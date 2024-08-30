FROM ubuntu:latest
ENV DEBIAN_FRONTEND=noninteractive
RUN apt-get update && apt-get upgrade -y
RUN apt-get install python3 -y
RUN apt-get install python3-pip -y
RUN rm /usr/lib/python*/EXTERNALLY-MANAGED
RUN pip3 install flask
RUN pip3 install Flask_cors
COPY ./api.py /app/api.py
WORKDIR /app
EXPOSE 5252
CMD ["python3", "api.py"]
