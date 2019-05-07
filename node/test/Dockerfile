ARG NODE_BASE_IMAGE
FROM $NODE_BASE_IMAGE
ONBUILD ARG test_project
ONBUILD ARG build_configuration
ONBUILD ENV TEST_PROJECT ${test_project}
ONBUILD ENV BUILD_CONFIGURATION ${build_configuration}

ONBUILD COPY tests /app/tests/
ONBUILD COPY application /app/application/
WORKDIR /app/

ONBUILD RUN npm ci /p:Configuration=$build_configuration \
        tests/$test_project

CMD npm test tests/$TEST_PROJECT --configuration $BUILD_CONFIGURATION
