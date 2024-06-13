ARG  VERSION=4.7.4

FROM quay.io/projectquay/clair:${VERSION} as src

FROM scratch
COPY --from=src / /
COPY config.yaml /config/config.yaml
COPY gitconfig /etc/gitconfig

# Copied from the original image
EXPOSE 6060 6061
ENTRYPOINT [ "/clair" ]
CMD ["-config=/config/config.yaml"]
