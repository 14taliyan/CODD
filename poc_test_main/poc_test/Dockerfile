
# Multi stage dockerfile
###########################################
# BASE IMAGE
###########################################
FROM python:3.8-slim-buster as build

WORKDIR /app

COPY . /app
RUN pip3 install -r requirements.txt

############################################
# HERE STARTS  MULTI STAGE BUILD
############################################

FROM gcr.io/distroless/python3
COPY --from=build /app /app
EXPOSE 5000
CMD  python ./main.py

## DockerFile