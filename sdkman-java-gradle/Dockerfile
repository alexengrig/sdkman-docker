FROM alexengrig/sdkman-java

ARG GRADLE_VERSION="7.6"
ENV GRADLE_VERSION=$GRADLE_VERSION

ENV GRADLE_HOME=$SDKMAN_DIR/candidates/gradle/current
ENV PATH=$GRADLE_HOME/bin:$PATH

RUN echo "Gradle version: '$GRADLE_VERSION'"

RUN bash -c "source $SDKMAN_DIR/bin/sdkman-init.sh && \
             yes | sdk install gradle $GRADLE_VERSION && \
             sdk flush"