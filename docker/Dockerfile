ARG NODE_VERSION
ARG ANGULAR_VERSION

FROM node:${NODE_VERSION}

ARG NODE_USER=appuser
ARG APP_NAME
ENV app_name=$APP_NAME

RUN npm install -g @angular/cli@${ANGULAR_VERSION}

RUN useradd -s /bin/false -m ${NODE_USER}

RUN mkdir -p /var/app
RUN chown -R ${NODE_USER}:${NODE_USER} /var/app

USER ${NODE_USER}
ENV PATH $PATH:./node_modules/.bin
WORKDIR /var/app

#RUN ng new test-app --minimal --routing --style scss --skip-git
#WORKDIR /var/app/test-app

#CMD [ "ng serve --open" ]
ENTRYPOINT /usr/local/bin/ng new $app_name --minimal --routing --style scss --skip-git
#CMD ["/bin/bash"]