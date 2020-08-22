# Dockerfile based on latest centos- nonprivilege user entry
FROM centos:latest
MAINTAINER abc <abc@example.com>
# -m will make the home directory (if not exists)
# -s will select the name of the user's login shell
RUN useradd -ms /bin/bash user
USER user
