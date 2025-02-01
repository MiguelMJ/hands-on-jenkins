# base image
FROM alpine:3.21

# Install python/pip
RUN apk add --update --no-cache python3 
RUN apk add py3-pip

# Install Python modules needed by the Python app
COPY requirements.txt /usr/src/app/
RUN pip install --break-system-packages --no-cache-dir -r /usr/src/app/requirements.txt

# Copy files required for the app to run
COPY app.py /usr/src/app/
COPY templates/index.html /usr/src/app/templates/

# Tell the port number the container should expose
EXPOSE 5000

# Run the application
CMD ["python3", "/usr/src/app/app.py"] 
