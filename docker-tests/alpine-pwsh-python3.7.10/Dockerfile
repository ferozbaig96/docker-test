# Dockerfile for alpine:latest with python 3.7.10 and powershell that works with "pwsh"

FROM alpine:latest

LABEL maintainer Feroz Baig <feroz.baig96.temp@gmail.com>

RUN apk add --no-cache ca-certificates less ncurses-terminfo-base krb5-libs libgcc libintl libssl1.1 libstdc++ tzdata userspace-rcu zlib icu-libs curl \
	python3-dev=3.7.10-r0 --repository=http://dl-cdn.alpinelinux.org/alpine/v3.10/main \
	&& \
	apk -X https://dl-cdn.alpinelinux.org/alpine/edge/main add --no-cache lttng-ust && \
	curl -L https://github.com/PowerShell/PowerShell/releases/download/v7.2.1/powershell-7.2.1-linux-alpine-x64.tar.gz -o /tmp/powershell.tar.gz && \
	mkdir -p /opt/microsoft/powershell/7 && \
	tar zxf /tmp/powershell.tar.gz -C /opt/microsoft/powershell/7 && \
	chmod +x /opt/microsoft/powershell/7/pwsh && \
    ln -s /opt/microsoft/powershell/7/pwsh /usr/bin/pwsh

ENTRYPOINT ["pwsh"]
