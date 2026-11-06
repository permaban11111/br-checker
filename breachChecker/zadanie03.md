1.

PS C:\Users\Student_EN\breachChecker\frontend> docker inspect --format '{{json .Config.Labels}}' adamdebniak-frontend:v1
{"autor":"Adam Debniak","data":"2026-11-06","maintainer":"student.student@student.com"}
PS C:\Users\Student_EN\breachChecker\frontend> docker history adamdebniak-frontend:v1
IMAGE          CREATED         CREATED BY                                      SIZE      COMMENT
d1cd45a0cc85   6 minutes ago   LABEL autor=Adam Debniak data=2026-11-06        0B        buildkit.dockerfile.v0
<missing>      6 minutes ago   EXPOSE [80/tcp]                                 0B        buildkit.dockerfile.v0
<missing>      6 minutes ago   RUN /bin/sh -c htmlhint /usr/share/nginx/htm…   4.1kB     buildkit.dockerfile.v0
<missing>      6 minutes ago   COPY . /usr/share/nginx/html # buildkit         32.8kB    buildkit.dockerfile.v0
<missing>      6 minutes ago   RUN /bin/sh -c apk add --no-cache nodejs npm…   99.3MB    buildkit.dockerfile.v0
<missing>      6 minutes ago   LABEL maintainer=student.student@student.com    0B        buildkit.dockerfile.v0
<missing>      14 hours ago    RUN /bin/sh -c set -x     && apkArch="$(cat …   52.4MB    buildkit.dockerfile.v0
<missing>      14 hours ago    ENV ACME_VERSION=0.4.1                          0B        buildkit.dockerfile.v0
<missing>      14 hours ago    ENV NJS_RELEASE=1                               0B        buildkit.dockerfile.v0
<missing>      14 hours ago    ENV NJS_VERSION=1.0.2                           0B        buildkit.dockerfile.v0
<missing>      15 hours ago    CMD ["nginx" "-g" "daemon off;"]                0B        buildkit.dockerfile.v0
<missing>      15 hours ago    STOPSIGNAL SIGQUIT                              0B        buildkit.dockerfile.v0
<missing>      15 hours ago    EXPOSE map[80/tcp:{}]                           0B        buildkit.dockerfile.v0
<missing>      15 hours ago    ENTRYPOINT ["/docker-entrypoint.sh"]            0B        buildkit.dockerfile.v0
<missing>      15 hours ago    COPY 30-tune-worker-processes.sh /docker-ent…   16.4kB    buildkit.dockerfile.v0
<missing>      15 hours ago    COPY 20-envsubst-on-templates.sh /docker-ent…   12.3kB    buildkit.dockerfile.v0
<missing>      15 hours ago    COPY 15-local-resolvers.envsh /docker-entryp…   12.3kB    buildkit.dockerfile.v0
<missing>      15 hours ago    COPY 10-listen-on-ipv6-by-default.sh /docker…   12.3kB    buildkit.dockerfile.v0
<missing>      15 hours ago    COPY docker-entrypoint.sh / # buildkit          8.19kB    buildkit.dockerfile.v0
<missing>      15 hours ago    RUN /bin/sh -c set -x     && addgroup -g 101…   5.75MB    buildkit.dockerfile.v0
<missing>      15 hours ago    ENV DYNPKG_RELEASE=1                            0B        buildkit.dockerfile.v0
<missing>      15 hours ago    ENV PKG_RELEASE=1                               0B        buildkit.dockerfile.v0
<missing>      15 hours ago    ENV NGINX_VERSION=1.31.8                        0B        buildkit.dockerfile.v0
<missing>      15 hours ago    LABEL maintainer=NGINX Docker Maintainers <d…   0B        buildkit.dockerfile.v0
<missing>      16 hours ago    CMD ["/bin/sh"]                                 0B        buildkit.dockerfile.v0
<missing>      16 hours ago    ADD alpine-minirootfs-3.24.4-x86_64.tar.gz /…   9.09MB    buildkit.dockerfile.v0
PS C:\Users\Student_EN\breachChecker\frontend>

Z mojego pliku mozna latwo zobaczyc ze pochodze warstwy od maintainer do autor=adamdebniak poniewaz wszystkie odziedziczone
z obrazu bazowego zostaly utworzone 14 godzin temu.
Niektore warstwy maja rozmiar 0b bo zmieniaja one wylacznie metadane i konfiguracje srodowiska a nic nie pobieraja lub instaluja
w wyniku inspect widac wartosc tylko mojej warstwy bo sa one budowane jedna na drugiej i nadpisuje ta poprzednia

2.
