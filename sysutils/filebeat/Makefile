# Created by: Palle Girgensohn <girgen@FreeBSD.org>
# $FreeBSD$

PORTNAME=	filebeat
PORTVERSION=	5.0.2
DISTVERSIONPREFIX=v
CATEGORIES=	sysutils

MAINTAINER=	girgen@FreeBSD.org
COMMENT=	Collect logs locally and send to remote logstash

LICENSE=	APACHE20

USE_GITHUB=	yes
GH_ACCOUNT=	elastic
GH_PROJECT=	beats

USES=		gmake go
GO_PKGNAME=	github.com/${GH_ACCOUNT}/${GH_PROJECT}
GO_TARGETS=	${PORTNAME}

USE_RC_SUBR=	${PORTNAME}

do-build:
	cd ${GO_WRKSRC}; ${SETENV} ${MAKE_ENV} ${GO_ENV} ${GMAKE} -C ${GO_TARGETS}

do-install:
	${INSTALL_PROGRAM} ${GO_WRKSRC}/${GO_TARGETS}/${GO_TARGETS} \
		${STAGEDIR}${PREFIX}/sbin
	${INSTALL_DATA} ${WRKSRC}/${GO_TARGETS}/${GO_TARGETS}.yml \
		${STAGEDIR}${PREFIX}/etc/${GO_TARGETS}.yml.sample

.include <bsd.port.mk>
