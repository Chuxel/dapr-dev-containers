FROM node:12-alpine as base

FROM base as devcontainer
WORKDIR /workspace
RUN apk add --no-cache curl bash \
    && curl -fsSL "https://raw.githubusercontent.com/microsoft/vscode-dev-containers/main/script-library/common-alpine.sh" -o /tmp/common.sh \
    && bash /tmp/common.sh \
    && rm /tmp/common.sh

FROM base as production
WORKDIR /app
COPY . .
RUN npm install
EXPOSE 3000
CMD [ "node", "app.js" ]
