FROM gliderlabs/alpine:latest

RUN apk-install dhcp
RUN ln -s /etc/dhcp/dhcpd.conf.example /etc/dhcp/dhcpd.conf; \
    touch /var/lib/dhcp/dhcpd.leases

# Why doesn't this work with CMD?
#ENTRYPOINT ["/usr/sbin/dhcpd"]

# Add script as a workaround for above.
COPY dhcpd /dhcpd
ENTRYPOINT ["/dhcpd"]

# Invoke these options unless user overrides at runtime.
CMD ["-t", "-cf /etc/dhcp/dhcpd.conf", "-lf /var/lib/dhcp/dhcpd.leases", "--no-pid", "-pf /dev/null"]
