# Created by: Nicola Stanislao Vitale <nivit@FreeBSD.org>
# $FreeBSD$

PORTNAME=	scudcloud
PORTVERSION=	1.64
DISTVERSIONPREFIX=	v
CATEGORIES=	net-im

MAINTAINER=	nivit@FreeBSD.org
COMMENT=	Desktop client app for Slack

LICENSE=	MIT
LICENSE_FILE=	${WRKSRC}/LICENSE

BUILD_DEPENDS=	${PYTHON_PKGNAMEPREFIX}jsmin>0:devel/py-jsmin@${PY_FLAVOR}
RUN_DEPENDS=	${PYTHON_PKGNAMEPREFIX}dbus>0:devel/py-dbus@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}sip>0:devel/py-sip@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}qt5-webkit>0:www/py-qt5-webkit@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}qt5-webkitwidgets>0:www/py-qt5-webkitwidgets@${PY_FLAVOR}

GH_ACCOUNT=	raelgc

HUNSPELL_RUN_DEPENDS=	${PYTHON_PKGNAMEPREFIX}hunspell>0:textproc/py-hunspell@${PY_FLAVOR} \
			qupzilla:www/qupzilla-qt5

INSTALLS_ICONS=	yes

OPTIONS_DEFINE=	HUNSPELL

USES=		python:3.4+
USE_GITHUB=	yes
USE_PYTHON=	autoplist distutils optsuffix

post-patch:
		@${REINPLACE_CMD} -i.bak -e 's,%%LOCALBASE%%,${LOCALBASE},1' \
			${WRKSRC}/share/${PORTNAME}.desktop \
			${WRKSRC}/${PORTNAME}/resources.py

.include <bsd.port.mk>
