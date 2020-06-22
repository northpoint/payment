FROM golang:1.7

RUN mkdir /app


COPY . $GOPATH/src/github.com/northpoint/payment/

WORKDIR $GOPATH/src/github.com/northpoint/payment/

RUN go get -u github.com/FiloSottile/gvt
RUN cd $GOPATH/src/github.com/northpoint/payment/ && gvt restore


RUN CGO_ENABLED=0 GOOS=linux go build -a -installsuffix cgo -o /app/main github.com/northpoint/payment/paymentsvc

CMD ["/go/src/app/main", "-port=80"]

#EXPOSE 80
