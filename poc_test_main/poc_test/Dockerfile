
# Multi stage dockerfile
###########################################
# BASE IMAGE
###########################################
FROM ubuntu as build

WORKDIR /app

COPY . /app
RUN apt-get update && \
    apt-get install -y python3 python3-pip && \
    pip install -r requirements.txt && \

############################################
# HERE STARTS  MULTI STAGE BUILD
############################################

FROM gcr.io/distroless/python3
COPY --from=build /app/ /app/
EXPOSE 5000
CMD  python ./main.py

## DockerFile single stage
# FROM python:3-alpine3.15

# WORKDIR /app

# COPY . /app

# RUN pip install -r requirements.txt



# EXPOSE 5000
# CMD  python ./main.py
