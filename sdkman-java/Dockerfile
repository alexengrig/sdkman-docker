FROM alexengrig/sdkman:0.1-SNAPSHOT

ARG JAVA_VERSION="17.0.5-oracle"
ENV JAVA_VERSION=$JAVA_VERSION

ENV JAVA_HOME=$SDKMAN_DIR/candidates/java/current
ENV PATH=$JAVA_HOME/bin:$PATH

RUN echo "Java version: '$JAVA_VERSION'"

RUN bash -c "source $SDKMAN_DIR/bin/sdkman-init.sh && \
             yes | sdk install java $JAVA_VERSION && \
             sdk flush"