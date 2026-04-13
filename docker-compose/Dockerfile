FROM oven/bun
WORKDIR /app
COPY . /app
RUN env
RUN echo "Build-time NPM_TOKEN is: $NPM_TOKEN"
RUN echo "Build-time SERVICE_PASSWORD_64_API is: $SERVICE_PASSWORD_64_API"
RUN bun install
HEALTHCHECK --interval=30s --timeout=10s --retries=3 \
CMD curl -f http://localhost:9999/health || exit 1
CMD bun start
