# Copyright: (c) 2022, Justin Béra (@just1not2) <me@just1not2.org>
# Apache License 2.0 (see LICENSE or https://www.apache.org/licenses/LICENSE-2.0.txt)

RELEASE_NAME=mystreama

default: install

download:
	helm dependency build charts/streama/
	helm plugin install https://github.com/karuppiah7890/helm-schema-gen

install:
	helm install ${RELEASE_NAME} charts/streama/

package:
	helm package charts/streama/ --destination packages/

template:
	helm template ${RELEASE_NAME} charts/streama/

uninstall:
	helm uninstall ${RELEASE_NAME}

values-schema:
	helm schema-gen charts/streama/values.yaml > charts/streama/values.schema.json
