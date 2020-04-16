#
# C-Util CI
#
# The 'c-util/c-util-ci' image builds on top of the official Fedora images
# and provides the build environment for the continuous integration of the
# c-util suite.
#

FROM fedora

RUN dnf \
        -y \
        -v \
        --nodocs \
        --setopt=install_weak_deps=False \
        install \
                audit-libs-devel \
                autoconf \
                automake \
                binutils-devel \
                bison-devel \
                clang \
                coreutils \
                dbus-daemon \
                dbus-devel \
                expat-devel \
                file \
                flex-devel \
                gawk \
                gcc \
                gdb \
                gettext \
                git \
                glib2-devel \
                glibc-devel \
                grep \
                groff \
                gzip \
                htop \
                iproute \
                libcap-ng-devel \
                libtool \
                libselinux-devel \
                lld \
                m4 \
                make \
                meson \
                ninja-build \
                patch \
                pkgconf \
                python3-docutils \
                rust \
                sed \
                strace \
                sudo \
                systemd-devel \
                tar \
                texinfo \
                util-linux \
                which \
                valgrind \
                vim \
        && dnf clean all

RUN dnf \
        -y \
        -v \
        --nodocs \
        --setopt=install_weak_deps=False \
        install \
                audit-libs-devel.i686 \
                dbus-devel.i686 \
                expat-devel.i686 \
                glibc-devel.i686 \
                libcap-ng-devel.i686 \
                libselinux-devel.i686 \
                systemd-devel.i686 \
                valgrind.i686 \
        && dnf clean all

COPY ci /ci
WORKDIR /ci/workdir
ENTRYPOINT ["/ci/run-suite"]
