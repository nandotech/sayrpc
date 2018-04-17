
# Build & push container image for GKE
buildgke:
	CGO_ENABLED=0 GOOS=linux go build -a -installsuffix cgo -ldflags '-w' -o app ./main.go
	sudo docker build -t gcr.io/nandotechinc/say:latest .
	rm -f app

pushgke:
	sudo gcloud docker -- push gcr.io/nandotechinc/say:latest

# Build & push container image for Azure
buildaks:
	CGO_ENABLED=0 GOOS=linux go build -a -installsuffix cgo -ldflags '-w' -o app ./main.go
	sudo docker build -t united.azurecr.io/say .
	rm -f app

pushaks:
	sudo docker push united.azurecr.io/say