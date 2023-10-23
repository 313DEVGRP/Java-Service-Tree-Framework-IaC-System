FROM fluentd:v1.9.1-debian-1.0

ENV TZ Asia/Seoul

USER root

RUN set -eux; \
    ln -snf /usr/share/zoneinfo/$TZ /etc/localtime; \
    echo ${TZ} > /etc/timezone; \
    gem install fluent-plugin-elasticsearch

RUN gem install fluent-plugin-kafka
RUN gem install fluent-plugin-grok-parser
RUN gem install fluent-plugin-rewrite-tag-filter
RUN gem install fluent-plugin-slack
RUN gem install fluent-plugin-record-modifier
RUN gem install fluent-plugin-multi-format-parser
RUN gem install fluent-plugin-anonymizer
RUN gem install fluent-plugin-s3

ADD fluent.conf /fluentd/etc/

USER fluent
