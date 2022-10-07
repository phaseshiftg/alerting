ARG DOCKER_VERSION_ARG
FROM opensearchstaging/opensearch:${DOCKER_VERSION_ARG}

ARG PLUGIN_ARG
ENV PLUGIN ${PLUGIN_ARG}

RUN if [ -d /usr/share/opensearch/plugins/opensearch-alerting ]; then \
      /usr/share/opensearch/bin/opensearch-plugin remove opensearch-alerting; \
    fi
ADD alerting/build/distributions/$PLUGIN /tmp/
RUN /usr/share/opensearch/bin/opensearch-plugin install --batch file:/tmp/$PLUGIN
