# Documento SPDX

Pregunta: ¿Tiene el paquete de software un documento SPDX asociado como expresión estándar de dependencias, licencias y problemas relacionados con la seguridad?

## Descripción

Un paquete de software tiene un documento SPDX asociado como expresión estándar de dependencias, licencias y problemas relacionados con la seguridad. Puede encontrar más información sobre la especificación SPDX en: https://spdx.org/

## Objetivos

Para los gerentes que adquieren software de código abierto como parte de una cartera de TI o de la Oficina de programas de código abierto, un documento SPDX proporciona una pieza central cada vez más esencial de información de gestión.  Esto surge porque, dado que existen paquetes de software en cadenas de suministro de software complejas, es importante expresar de forma clara y estandarizada las dependencias asociadas, las licencias y los problemas relacionados con la seguridad con ese paquete de software. Un documento SPDX proporciona una única fuente de información tanto para uso interno como para la distribución posterior de paquetes de software. Un documento SPDX ayuda a determinar cómo las organizaciones rutinizan el trabajo de código abierto para integrarse mejor con sus propias rutinas de gestión de riesgos de código abierto.

## Implementación

### Filtros

[augur-SPDX](https://github.com/chaoss/augur-spdx) se utilizó para escanear el repositorio [GitHub Zephyr](https://github.com/zephyrproject-rtos/zephyr). Estas son las licencias identificadas por el escaneo en formato JSON:
```
{
  "0": "Apache-2.0",
  "1": "BSD-2-Clause",
  "2": "BSD-3-Clause",
  "3": "GPL-2.0",
  "4": "GPL-2.0+",
  "5": "GPL-3.0+",
  "6": "ISC",
  "7": "MIT"
  "8": "BSD-4-Clause-UC",
  "9": "CC0-1.0"
}
```
Este documento fue generado por Augur.

## Herramientas que proporcionan la métrica

* [DoSOCSv2](https://github.com/DoSOCSv2/DoSOCSv2) integrado como servicio de [Augur](https://github.com/chaoss/augur). Se puede obtener un documento SPDX archivo por archivo configurando Augur mediante el complemento DoSOCSv2.  Las partes relevantes del esquema de la base de datos se ilustran a continuación.
* [Augur-SPDX](https://github.com/chaoss/augur-spdx) integrado como servicio de [Augur](https://github.com/chaoss/augur). Se puede obtener un documento SPDX archivo por archivo configurando Augur mediante el complemento augur-spdx, que deriva de DOSOCS.  Las partes relevantes del esquema de la base de datos se ilustran a continuación. Esta implementación es una bifurcación de DoSOCSv2.

* Paquetes
* Package_Files
* Archivos (que pueden estar incluidos, pero es poco probable que también se incluyan en otros paquetes). La información de la licencia se incluye como parte de un SBOM, pero la complejidad de la identificación de la licencia se aclara en las métricas [License_Count](https://github.com/chaoss/wg-risk/blob/master/metrics/License_Count.md), [License_Coverage](https://github.com/chaoss/wg-risk/blob/master/metrics/License_Coverage.md)y [License_Declared](https://github.com/chaoss/wg-risk/blob/master/metrics/License_Declared.md).

![SBOM](images/spdx-document_sbom.png)


## Referencias

* https://spdx.org
* https://www.ntia.doc.gov/SoftwareTransparency  


