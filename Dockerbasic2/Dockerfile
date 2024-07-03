###########################################
# BASE IMAGE
###########################################
# Dockerfile
FROM golang:latest AS build

WORKDIR /app

COPY . .

RUN CGO_ENABLED=0 go build -o /app/app .

# Final stage
FROM scratch

COPY --from=build /app/app /app/app

CMD ["/app/app"]
