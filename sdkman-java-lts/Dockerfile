FROM alexengrig/sdkman:0.1-SNAPSHOT

ARG JAVA_8_VERSION="8.0.302-open"
ENV JAVA_8_VERSION=$JAVA_8_VERSION

ARG JAVA_11_VERSION="11.0.12-open"
ENV JAVA_11_VERSION=$JAVA_11_VERSION

ARG JAVA_17_VERSION="17.0.5-oracle"
ENV JAVA_17_VERSION=$JAVA_17_VERSION

ARG JAVA_DEFAULT_VERSION=$JAVA_8_VERSION
ENV JAVA_DEFAULT_VERSION=$JAVA_DEFAULT_VERSION

ENV JAVA_HOME=$SDKMAN_DIR/candidates/java/current
ENV PATH=$JAVA_HOME/bin:$PATH

RUN echo "Java 8 version: '$JAVA_8_VERSION'"
RUN echo "Java 11 version: '$JAVA_11_VERSION'"
RUN echo "Java 17 version: '$JAVA_17_VERSION'"
RUN echo "Default Java version: '$JAVA_DEFAULT_VERSION'"

RUN bash -c "source $SDKMAN_DIR/bin/sdkman-init.sh && \
             yes | sdk install java $JAVA_8_VERSION && \
             yes | sdk install java $JAVA_11_VERSION && \
             yes | sdk install java $JAVA_17_VERSION && \
             sdk flush"

CMD bash -c "source $SDKMAN_DIR/bin/sdkman-init.sh && \
             sdk default java $JAVA_DEFAULT_VERSION"