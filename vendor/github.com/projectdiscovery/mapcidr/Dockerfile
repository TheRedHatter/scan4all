FROM golang:1.18.3-alpine AS build-env
RUN go install -v github.com/projectdiscovery/mapcidr/cmd/mapcidr@latest

FROM alpine:3.17.3
COPY --from=build-env /go/bin/mapcidr /usr/local/bin/mapcidr
ENTRYPOINT ["mapcidr"]
