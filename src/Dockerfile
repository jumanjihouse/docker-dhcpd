FROM gliderlabs/alpine:latest

RUN apk-install dhcp
RUN touch /var/lib/dhcp/dhcpd.leases

# Allow to attach data containers.
VOLUME ["/etc/dhcp", "/var/lib/dhcp"]

# Why doesn't this work with CMD?
#ENTRYPOINT ["/usr/sbin/dhcpd"]

# Add script as a workaround for above.
COPY dhcpd /dhcpd
ENTRYPOINT ["/dhcpd"]

# Invoke these options unless user overrides at runtime.
CMD ["-t", "-cf /etc/dhcp/dhcpd.conf.example"]
