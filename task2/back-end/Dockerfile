FROM ubuntu:latest
ENV DEBIAN_FRONTEND=noninteractive
RUN apt-get update && apt-get upgrade -y
RUN apt-get install python3 -y
RUN apt-get install python3-pip -y
RUN rm /usr/lib/python*/EXTERNALLY-MANAGED
RUN pip3 install flask
RUN echo "#!/usr/bin/env python3\n\nfrom flask import Flask\n\napp = Flask(__name__)\n\n@app.route('/api/hello')\ndef hello_world():\n\treturn 'Hello, World!'\n\nif __name__ == '__main__':\n\tapp.run(host='0.0.0.0', port=5252)\n" >> api.py
RUN chmod +x api.py
WORKDIR /app
COPY ./api.py /app/api.py
EXPOSE 5252
CMD ["python3", "api.py"]
