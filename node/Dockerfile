ARG NODE_BASE_IMAGE
FROM $NODE_BASE_IMAGE
ONBUILD ARG application
ONBUILD ARG friendly
ONBUILD ARG build_hash
ONBUILD ARG build_branch
ONBUILD ARG build_user
ONBUILD ARG build_number
ONBUILD ARG build_group

WORKDIR /app

ONBUILD COPY application/package.json .
ONBUILD COPY application/package-lock.json .

ONBUILD RUN npm ci

ONBUILD COPY application .

ONBUILD RUN echo "application=$application">metadata.txt && \
    echo "friendly=$friendly">>metadata.txt && \
    echo "build_date=$(date -u)">>metadata.txt && \
    echo "build_hash=$build_hash">>metadata.txt && \
    echo "build_branch=$build_branch">>metadata.txt && \
    echo "build_group=$build_group">>metadata.txt && \
    echo "build_user=$build_user">>metadata.txt && \
    echo "build_number=$build_number">>metadata.txt

ONBUILD ENV PATH /app/node_modules/.bin:$PATH
