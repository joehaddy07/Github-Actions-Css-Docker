# syntax=docker/dockerfile:1
ARG VERSION=1.25

FROM nginx:${VERSION}-alpine-slim AS base

LABEL Maintainer="Joseph Haddison" \
      Email="joelhaddy07@gmail.com" \
      Team="SRE"

ENV WORK_DIR=/usr/share/nginx/html

WORKDIR ${WORK_DIR}

COPY . ${WORK_DIR}

EXPOSE 80

HEALTHCHECK --interval=30s --timeout=10s --start-period=5s --retries=3 \
  CMD curl -f http://localhost/index.html || exit 1

CMD ["nginx", "-g", "daemon off;"]