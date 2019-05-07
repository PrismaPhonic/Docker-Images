ARG NODE_BASE_IMAGE
FROM $NODE_BASE_IMAGE

WORKDIR /app
ONBUILD COPY --from=builder /application/ /app/
ONBUILD COPY --from=builder /application/metadata.txt /app/metadata.txt

CMD npm run nodemon --watch 'src/**/*.ts' --exec 'ts-node' src/index.ts
