ARG BASE_IMAGE
FROM $BASE_IMAGE

ARG DEV_COMMON=/common
ARG PROJECT_NAME

ENV BUNDLE_SILENCED_ROOT_WARNING="true"
ENV DEV_COMMON="$DEV_COMMON"
RUN \
  ln --symbolic --force "$DEV_COMMON/profile/dev-profile.sh" /etc/profile.d/dev-profile.sh ; \
  echo "[[ -f \"$DEV_COMMON/profile/.bashrc\" ]] && source \"$DEV_COMMON/profile/.bashrc\"" >> /root/.bashrc ; \
  gem install solargraph debug --no-document

ENV PROJECT_NAME="$PROJECT_NAME"
ENV PATH="/$PROJECT_NAME/bin:$PATH"
WORKDIR "/$PROJECT_NAME"
