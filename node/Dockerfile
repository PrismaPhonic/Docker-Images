ARG NODE_BASE_IMAGE
FROM $NODE_BASE_IMAGE
ONBUILD ARG build_project
ONBUILD ENV BUILD_PROJECT ${build_project}

WORKDIR /app
ONBUILD COPY --from=builder /src/out /app/
ONBUILD COPY --from=builder /src/metadata.txt /app/metadata.txt

CMD npm start
