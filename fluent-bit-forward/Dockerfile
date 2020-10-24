FROM fluent/fluent-bit:latest

# Configuration files
COPY conf/fluent-bit.conf /fluent-bit/etc/

# Entry point
CMD ["/fluent-bit/bin/fluent-bit", "-c", "/fluent-bit/etc/fluent-bit.conf"]