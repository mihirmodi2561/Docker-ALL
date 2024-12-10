# HealthCheck Instruction

- Docker how to test a container to check that it's still working
- This can detect cases such as a
  - web server stuck in a loop, unable to handle new connections even if still running

**--no-cache: This flag tells Docker to ignore any cached layers and build each layer from scratch.**

HEALTHCHECK --interval=30s \
            --timeout=30s \
            --start-period=0s \
            --retries=3 \
            CMD curl -f http://localhost/ || exit 1

