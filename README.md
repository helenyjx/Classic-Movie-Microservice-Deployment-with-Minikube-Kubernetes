# Jiaxin-P2-Microservice-MininKube-Rust

## Key Objectives of Project
In project 2, the purpose is to build a functional Web Microservice in Rust based on Kubernetes or other similar platforms (Kubernetes Deployments provide a higher-level abstraction for managing the deployment and scaling of applications in a cluster, making it easier to automate and manage the process).
I create a simple actix Microservice for movie buffs which can be used for randomly choosing a good classic movie at leisure based on the list of the world top 10 best movies. 

This actix Microservice has multiple routes:

A. type: "/" that returns a message : "Hello, random best movies around the world!"

B. type: "/movie" that returns a random best movie in the list of the world top 10 best movies

C. type: "/version" that returns the version of the service 

## Structure Diagram
<img width="508" alt="Screen Shot 2023-02-23 at 1 20 18 AM" src="https://user-images.githubusercontent.com/112274822/220833875-65fe01c5-aed8-4ccc-b9ed-cdbdc0e1dba9.png"><img width="735" alt="Screen Shot 2023-02-23 at 1 09 20 AM" src="https://user-images.githubusercontent.com/112274822/220833906-cad3f3b6-59ef-4079-ac69-2eaabafbde70.png">

## Demo Video Link
https://teams.microsoft.com/l/message/19:48a1400da82046de9da6bbe430b981d2@thread.tacv2/1677216347453?tenantId=cb72c54e-4a31-4d9e-b14a-1ea36dfac94c&groupId=7757ff33-20f5-434b-8d0b-5fe61b251c34&parentMessageId=1677216347453&teamName=IDS-721-Spring-2023&channelName=Week%206%20Individual%20Project%202&createdTime=1677216347453&allowXTenantAccess=false

## Preparation
### 1. Containerization: Setup virtual environment
A virtual environment is a tool that helps to keep dependencies required by different projects separate by creating isolated python virtual environments for them. 
* Type: `python3 -m venv env` and `source env/bin/activate`

### 2. Instal Rust
* Type: `curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh` and then `source "$HOME/.cargo/env"`

### 3. create new project
* Type: `cargo new (project name)` (my Eg: `cargo new src`)
* Create main.rs and lib.rs for the src project
* Cargo build: it is a command in the Rust programming language that is used to compile a Rust project. It compiles the project's source code and its dependencies, and produces an executable binary file. The `cargo build` command can be run from the root directory of the project.
* Set up Cargo.toml to determine the dependencies and build configuration of the project.
<img width="728" alt="Screen Shot 2023-02-09 at 1 42 11 PM" src="https://user-images.githubusercontent.com/112274822/217907444-fb11682a-6699-493b-a945-17fd73c8888a.png">

* Set up Dockerfile for APP webdocker
<img width="489" alt="Screen Shot 2023-02-09 at 1 45 39 PM" src="https://user-images.githubusercontent.com/112274822/217908173-d0f572ee-847a-4be6-b1fc-18108e0d62c9.png">

* Create a Makefile: it is a special file that lists a set of rules for compiling a project. These rules include targets, which can be an action make needs to take or the files/objects make will need to build, and the commands that need to be run in order to build that target. 
<img width="354" alt="Screen Shot 2023-02-09 at 1 51 30 PM" src="https://user-images.githubusercontent.com/112274822/217909371-9e17b610-ec15-47dc-9a0b-eff5163b287b.png">

## Run Microservice
### 1. Use `make format` and `make lint` to fix code format and check code errors
<img width="544" alt="Screen Shot 2023-02-09 at 2 06 34 PM" src="https://user-images.githubusercontent.com/112274822/217913027-44f99e34-1d47-4197-a37a-9ffc3a13ed7d.png">

### 2. Run web microservice 
* After creating main.rs and lib.rs, in terminal, directly type: `cargo run` (Press CTRL+C to quit)
<img width="515" alt="Screen Shot 2023-02-09 at 2 07 26 PM" src="https://user-images.githubusercontent.com/112274822/217913210-375631a1-f8c3-4ce4-9a0a-8945059485ab.png">

* Usage of an example (Test the URL): https://helenyjx-ubiquitous-guide-v957g7j5xjqfvgx-8080.preview.app.github.dev/movie

* A. type: "/" that returns a message : "Hello, random best movies around the world!"
<img width="642" alt="Screen Shot 2023-02-09 at 2 01 26 PM" src="https://user-images.githubusercontent.com/112274822/217912099-51c491d1-59f3-4006-aaa8-c1f38ef4598c.png">

* B. type: "/movie" that returns a random best movie in the list of the world top 10 best movies
<img width="697" alt="Screen Shot 2023-02-09 at 2 02 33 PM" src="https://user-images.githubusercontent.com/112274822/217912257-f90b27dd-ad64-4bb3-8746-f6419320cac7.png">

* C. type: "/version" that returns the version of the service 
<img width="701" alt="Screen Shot 2023-02-09 at 2 04 38 PM" src="https://user-images.githubusercontent.com/112274822/217912657-35ce00a3-cadd-4251-808a-c367e0e5c1c6.png">

## Use automatic deployment platforms to deploy the project
### A. Via AWS APP Runner

1. Go to github and then copy the http link for cloning my repo of the project 2

<img width="993" alt="Screen Shot 2023-02-09 at 4 32 23 PM" src="https://user-images.githubusercontent.com/112274822/217944275-01f1edb5-41ab-4be3-9db3-674cfce23fa8.png">

2. Go to AWS Cloud9, then click "Create environment"
<img width="1039" alt="Screen Shot 2023-02-09 at 4 35 43 PM" src="https://user-images.githubusercontent.com/112274822/217944516-734f0e95-e0cc-4392-9216-e4181919b2d2.png">

* In the terminal, copy the clone link and type : `git clone https://github.com/nogibjj/Jiaxin-P2-Microservice-Rust.git`
* Install Rust again
<img width="1284" alt="Screen Shot 2023-02-09 at 4 48 15 PM" src="https://user-images.githubusercontent.com/112274822/217947005-6a91ea81-7a18-41f8-8c62-0c4cb0a482d4.png">

3. Go to AWS Amazon Elastic Container Registry, click "get start"
* Then follow below steps to create a private repository
<img width="993" alt="Screen Shot 2023-02-09 at 4 50 15 PM" src="https://user-images.githubusercontent.com/112274822/217947261-ede4ea1c-2533-479d-9b9c-ad1571c17a7a.png">
<img width="895" alt="Screen Shot 2023-02-09 at 4 52 05 PM" src="https://user-images.githubusercontent.com/112274822/217947658-d9452c70-d0d7-42db-8c04-f39110c3dbb4.png">
<img width="885" alt="Screen Shot 2023-02-09 at 4 52 22 PM" src="https://user-images.githubusercontent.com/112274822/217947717-0166f817-5709-4ee5-b856-ec3a57bd3b9f.png">

* Then go to "images", click "View push commands" to copy the code, then run each of them one by one at AWS Cloud9 later.
<img width="1455" alt="Screen Shot 2023-02-09 at 4 54 10 PM" src="https://user-images.githubusercontent.com/112274822/217948051-2950f3e8-c772-4aa6-bad8-7f20fb8bd119.png">
<img width="886" alt="Screen Shot 2023-02-09 at 4 56 40 PM" src="https://user-images.githubusercontent.com/112274822/217948452-90e17702-10b6-4803-849d-6beb1d94210e.png">

* **Tips**: Sometimes you maybe occur an error when doing docker build, just type: `curl -s https://gist.githubusercontent.com/wongcyrus/a4e726b961260395efa7811cab0b4516/raw/6a045f51acb2338bb2149024a28621db2abfcaab/resize.sh | bash /dev/stdin 60` to fix it
<img width="1190" alt="Screen Shot 2023-02-08 at 5 00 21 PM" src="https://user-images.githubusercontent.com/112274822/217949943-280eed30-3802-4f14-8aa8-62a6d109fd9e.png">

* Copy above code in terminal at AWS Cloud9
<img width="1183" alt="Screen Shot 2023-02-09 at 4 58 06 PM" src="https://user-images.githubusercontent.com/112274822/217948727-afbe6832-e06c-4ce7-9a3d-5c458e4245e9.png">
<img width="1155" alt="Screen Shot 2023-02-09 at 5 00 07 PM" src="https://user-images.githubusercontent.com/112274822/217949064-b97e3b1b-a09e-49c2-bebb-3fc8ddc0dc78.png">

4. Go to AWS APP Runner
* Click "create service" to set up configuration by following below steps:

<img width="1343" alt="Screen Shot 2023-02-09 at 5 10 25 PM" src="https://user-images.githubusercontent.com/112274822/217951010-39109382-8674-4194-b341-1e959221f8a5.png">
<img width="685" alt="Screen Shot 2023-02-09 at 5 16 48 PM" src="https://user-images.githubusercontent.com/112274822/217951860-e6d68cb1-1e5b-49d6-b548-c741f04ec1f0.png">
<img width="682" alt="Screen Shot 2023-02-09 at 5 17 40 PM" src="https://user-images.githubusercontent.com/112274822/217951961-977e7d11-6d55-4d62-935f-1d05b8a8b17d.png">

* Then begin to depoly the project after click "Deploy", make sure the event status are "Succeeded" at Deployment logs, otherwise you need to fix the errors according to the report from the event log.
<img width="1361" alt="Screen Shot 2023-02-09 at 5 18 47 PM" src="https://user-images.githubusercontent.com/112274822/217952146-282eb6f1-68e5-46ae-8ed9-0e5ec71638f7.png">
<img width="1340" alt="Screen Shot 2023-02-09 at 5 22 31 PM" src="https://user-images.githubusercontent.com/112274822/217952763-c3951e1b-e178-4e79-838c-ab6bf6347341.png">

### B. Via Lab Minikube

1. Push container to DockerHub: 
* Example of a pushed FastAPI container here: https://hub.docker.com/repository/docker/helenyjx/rust-mini/general
```
docker login -u helenyjx
docker build . -t helenyjx/rust-mini
docker push helenyjx/rust-mini
```
<img width="668" alt="Screen Shot 2023-02-23 at 11 31 59 PM" src="https://user-images.githubusercontent.com/112274822/221098074-b1fc3556-3f47-48fb-b77d-26d8396417a8.png">
<img width="948" alt="Screen Shot 2023-02-23 at 11 31 20 PM" src="https://user-images.githubusercontent.com/112274822/221098018-b5cc91a2-668a-4399-ad92-84b38b777996.png">

2. Run `minikube start` to start cluster
<img width="845" alt="Screen Shot 2023-02-22 at 10 28 22 PM" src="https://user-images.githubusercontent.com/112274822/220824656-ff94c58d-3049-4b78-863d-b240985ee834.png">

3. Run `minikube dashboard --url` to view dashboard in a new terminal, then go to "PORTS" find 36775, open the link and add "api" in the end of the link
<img width="760" alt="Screen Shot 2023-02-22 at 10 54 29 PM" src="https://user-images.githubusercontent.com/112274822/220825196-c6a02ff1-afdd-4abf-8a1c-09d7c332894f.png">

<img width="1015" alt="Screen Shot 2023-02-22 at 10 55 14 PM" src="https://user-images.githubusercontent.com/112274822/220825235-cda7d599-56b4-4f13-aec1-15ba5348390a.png">

<img width="701" alt="Screen Shot 2023-02-22 at 10 53 58 PM" src="https://user-images.githubusercontent.com/112274822/220825313-c098e68c-f91f-41d6-a0aa-070ed039b711.png">

4. Hover over link and "follow link"
5. Create a deployment: `kubectl create deployment hi-minikube --image=registry.hub.docker.com/helenyjx/rust-mini`
6. View deployment: `kubectl get deployments`
7. Create service and expose it: `kubectl expose deployment hi-minikube --type=LoadBalancer --port=8080`
8. View services:
```
kubectl get service hi-minikube
minikube service hi-minikube  --url
```
9. Curl web service: i.e. `curl http://192.168.49.2:31693`
10. Depoly the project via below link:
```
curl http://192.168.49.2:31693/movie
curl http://192.168.49.2:31693/version
```
<img width="1021" alt="Screen Shot 2023-02-23 at 11 30 57 PM" src="https://user-images.githubusercontent.com/112274822/221097950-b90dbb8f-0f15-4c5b-889e-1eba08334a65.png">

11. Cleanup:
```bash
kubectl delete service hello-node
kubectl delete deployment hello-node
minikube stop
````

## References

* [FastAPI Docker docs](https://github.com/tiangolo/uvicorn-gunicorn-fastapi-docker)
* [Hello minikube](https://kubernetes.io/docs/tutorials/hello-minikube/)
* [Reference](https://kubernetes.io/blog/2019/07/23/get-started-with-kubernetes-using-python/)
* [Professor's tutorial](https://github.com/nogibjj/coursera-applied-de-kubernetes-lab)
