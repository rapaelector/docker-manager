# https://github.com/elastic/logstash-docker
FROM docker.elastic.co/logstash/logstash:5.6.3

# Add your logstash plugins setup here
# Example: RUN logstash-plugin install logstash-filter-json
RUN logstash-plugin install logstash-filter-json
RUN logstash-plugin install logstash-filter-grok
RUN logstash-plugin install logstash-filter-mutate
RUN logstash-plugin install logstash-filter-ruby
RUN logstash-plugin install x-pack