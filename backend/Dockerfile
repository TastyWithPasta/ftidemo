FROM python:3.9-slim-buster

# Copy app code
COPY ./app /opt/app
WORKDIR /opt/app

# Install app dependencies
COPY requirements.txt /opt/app/
RUN mkdir -p /opt/app/pip_cache
RUN pip install -r requirements.txt --cache-dir /opt/app/pip_cache

# Create user and add ownership
RUN useradd -d /home/fti -m -s /bin/bash fti
RUN chown -R fti /opt/app
USER fti
EXPOSE 5000
STOPSIGNAL SIGTERM
CMD ["bash", "/opt/app/start.sh"]