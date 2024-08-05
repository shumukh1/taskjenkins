FROM golang:1.22-alpine as builder
 
WORKDIR /app
 
COPY . .

RUN go build -o main .
 
FROM scratch
 
COPY --from=builder /app/main /app/main
 
USER 1000:1000
 
EXPOSE 8080
 
 
CMD ["/app/main"]
