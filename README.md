# Say gRPC Server

### Follows Francesc Campoy's tutorial in Just For Func #12 and 13 to create a gRPC-based Text-to-Spech server.

* Text-to-speech server that will convert anything passed to speech
* Server-Client communication is done using gRPC/Protobufs
* Utilize Makefiles to automate build process/pipelien
* Backend (server) is containerized using Docker
* Contained on Kubernetes using GKE


#### For `/backend/` (server)

1. `make build` builds the go binary & then the docker image, tagging it to our GKE repo.
2. `make push` tags our container and pushes it up to GCR

#### For `/api/`

1. `make build` runs required `protoc` command to compile our `say.proto` into `Go`.

#### `/say/` is our client code, to be run locally.