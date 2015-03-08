FROM gliderlabs/alpine:latest
RUN apk-install nagios-plugins
ENTRYPOINT ["/usr/lib/nagios/plugins/check_dhcp"]
