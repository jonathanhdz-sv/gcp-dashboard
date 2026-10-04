# Sesion movil — VPC

## Objetivo

Preparar la semana 9 del plan GCP: VPC, subnets, rutas, firewall y peering.

No es necesario abrir la consola desde el iPhone. Esta parte es teoria; el hands-on se hara cuando vuelva a usar la computadora.

## Resumen rapido

- **VPC network:** recurso global que contiene la red.
- **Subnet:** recurso regional con un rango CIDR, por ejemplo `10.10.1.0/24`.
- **VM:** recurso zonal dentro de una subnet regional.
- **Route:** indica hacia donde enviar el trafico. Se elige la ruta mas especifica.
- **Firewall rule:** controla trafico de entrada o salida y se aplica a las VMs objetivo. Es stateful.
- **Subnet publica o privada:** una subnet no es publica solo por su nombre. La exposicion depende de IP externa, rutas, NAT y firewall.
- **VPC peering:** conecta dos VPC de forma privada. Los rangos no deben solaparse y el peering no es transitivo.

## Regla importante de seguridad

En una VPC personalizada no se debe abrir SSH a todo Internet. La regla correcta para el laboratorio sera permitir TCP `22` solamente desde la IP publica propia.

## Quiz — responder en ingles

1. Is a VPC global or regional?
2. Are subnets global, regional, or zonal?
3. What does a route determine?
4. What is the safest source range for an SSH firewall rule?
5. Why can two peered VPC networks not use overlapping IP ranges?

Responder desde el iPhone con este formato:

```text
1. ...
2. ...
3. ...
4. ...
5. ...
```

## Siguiente practica en computadora

Crear una VPC personalizada con:

- `subnet-public`: `10.10.1.0/24`
- `subnet-private`: `10.10.2.0/24`
- Regla SSH TCP `22` solo desde la IP propia

No marcar la sesion como terminada hasta responder el quiz y ejecutar la practica.

## Temario completo

### Fase 1 — Base

1. Linux CLI: navegacion, pipes, `grep` y redireccion.
2. Linux: `chmod`, `chown`, usuarios, grupos y `sudo`.
3. Linux networking: `ping`, `curl`, `tcpdump`, `ss` y `netstat`.
4. Mock interview de Linux y REST en ingles.
5. REST API y HTTP: metodos, status codes, headers y JSON.
6. Git: clone, branches, merge, pull requests y `.gitignore`.
7. IAM y jerarquia GCP: organization, folders y projects.
8. Mock interview de REST, Git e IAM en ingles.

### Fase 2 — Core GCP

9. VPC: subnets, rangos IP, rutas y peering.
10. Firewall rules en la consola GCP.
11. Compute Engine: tipos de VM, discos, snapshots e imagenes.
12. Compute Engine: SSH, metadata y startup scripts.
13. Cloud Storage: buckets, clases de almacenamiento y lifecycle.
14. Cloud Storage y Cloud SQL: practica en consola.
15. Cloud Spanner y comparacion SQL/NoSQL: Bigtable, Firestore y Memorystore.
16. Mock interview de Storage, bases de datos y troubleshooting.

### Fase 3 — Cierre

17. Serverless: App Engine, Cloud Functions y Cloud Run.
18. Deploy de una Cloud Function.
19. Docker: imagenes, Dockerfile, `docker run` y Docker Compose.
20. Kubernetes: pods, services, deployments y GKE.
21. Simulacro de las dos entrevistas orales en ingles.
22. Simulacro de prueba practica en vivo.

### Temas transversales

- OSI, TCP/IP, IP addressing y subnetting.
- Troubleshooting de conectividad y servicios.
- Practica verbal en ingles al final de cada bloque.
- Hands-on obligatorio en consola para VPC, firewall, Compute, Storage y Cloud Functions.

## Temario integral necesario para GCP Cloud Support Engineer

GCP tiene cientos de productos. Para este objetivo no hace falta estudiar cada producto con la misma profundidad; hay que dominar los fundamentos y los servicios que aparecen en operaciones y troubleshooting.

### 1. Fundamentos de Google Cloud

- Cloud computing, responsabilidad compartida, regiones y zonas.
- Projects, folders, organizations, APIs y Service Usage.
- Google Cloud Console, Cloud Shell, `gcloud` y documentacion oficial.
- Labels, quotas, limits y resource locations.
- Billing accounts, budgets, alerts y control de costos.

### 2. Linux, redes y programacion base

- Linux CLI, permisos, procesos, servicios, usuarios y logs.
- Bash, pipes, redireccion y herramientas de diagnostico.
- OSI, TCP/IP, IPv4, CIDR, subnetting, DNS, DHCP, NAT y puertos.
- HTTP/HTTPS, TLS, REST, JSON, status codes y curl.
- Git y Python basico para scripts de soporte.

### 3. IAM y administracion de recursos

- Principals, groups, roles basicos, predefinidos y custom.
- IAM policies, herencia, condiciones y least privilege.
- Service accounts, impersonation, Workload Identity y rotacion de credenciales.
- Organization policies, Resource Manager y audit logs.
- API keys, OAuth y por que evitar service account keys permanentes.

### 4. Networking GCP

- VPC global, subnets regionales, rangos IP, rutas y peering.
- Auto mode vs custom mode y Shared VPC.
- Firewall rules, hierarchical firewall, tags y service accounts como targets.
- Cloud NAT, Cloud Router y BGP.
- Cloud VPN, Cloud Interconnect y Private Google Access.
- Private Service Connect y VPC Service Controls.
- Cloud DNS, Network Connectivity Center y Connectivity Tests.
- Load Balancing: external, internal, proxy, passthrough y global/regional.
- Cloud CDN y Cloud Armor.

### 5. Compute

- Compute Engine: tipos de maquina, imagenes, discos y ciclo de vida.
- Persistent Disk, Local SSD, snapshots, images y backups.
- SSH, OS Login, IAP, metadata, startup scripts y guest agent.
- Managed Instance Groups, instance templates y autoscaling.
- Health checks, failover y troubleshooting de VMs.

### 6. Storage

- Cloud Storage: buckets, objetos, ubicaciones y clases.
- IAM, uniform bucket-level access, ACLs y signed URLs.
- Versioning, lifecycle, retention policies, holds y soft delete.
- Cifrado Google-managed y CMEK con Cloud KMS.
- Subidas, descargas, permisos, transferencia y troubleshooting.
- Filestore y diferencias entre object, block y file storage.

### 7. Bases de datos y datos

- Cloud SQL: engines, conexiones, backups, HA, replicas y maintenance.
- AlloyDB: concepto y casos de uso.
- Cloud Spanner: escala global y consistencia.
- Firestore: documentos, colecciones, indexes y reglas.
- Bigtable: wide-column, row keys y escala.
- Memorystore: cache Redis/Memcached.
- BigQuery: datasets, tables, queries, permisos y costos.
- Diferencias entre SQL, NoSQL, object storage, cache y data warehouse.

### 8. Containers y serverless

- Docker: imagenes, Dockerfile, registry, `docker run` y Compose.
- Artifact Registry y vulnerabilidades de imagenes.
- GKE: clusters, nodes, pools, pods, deployments y services.
- GKE: ingress/gateway, ConfigMaps, Secrets, RBAC y autoscaling.
- Kubernetes logs, events, probes, rollout y rollback.
- Cloud Run: revision, traffic, concurrency, regions y service account.
- Cloud Functions: triggers, runtime, permisos, logs y deploy.
- App Engine: services, versions, scaling y traffic migration.

### 9. Integracion y aplicaciones

- Pub/Sub: topics, subscriptions, acknowledgements, retry y dead-letter.
- Eventarc, Cloud Scheduler y Workflows.
- API Gateway y conceptos basicos de Apigee.
- Cloud Tasks y patrones asincronos.

### 10. Observabilidad y operaciones

- Cloud Logging, Log Explorer, sinks, exclusions y log-based metrics.
- Cloud Monitoring, dashboards, alert policies, uptime checks y SLOs.
- Error Reporting, Cloud Trace y Cloud Profiler.
- Ops Agent, metricas de VM y auditoria de actividad.
- Incidentes, severidad, timeline, evidencia y escalamiento.

### 11. Seguridad

- Shared responsibility, least privilege y defense in depth.
- Secret Manager, Cloud KMS y cifrado.
- Security Command Center y vulnerabilidades.
- VPC Service Controls, Cloud Armor y Binary Authorization.
- IAM audit, policy troubleshooter y acceso temporal.

### 12. DevOps e infraestructura

- Cloud Build, Artifact Registry y Cloud Deploy.
- CI/CD, ramas, pull requests y rollback.
- Terraform: provider, state, plan, apply y variables.
- Infraestructura reproducible y configuracion por ambientes.

### 13. Fiabilidad, rendimiento y costos

- Alta disponibilidad, redundancia zonal/regional y disaster recovery.
- RTO, RPO, backups, replicas y restauracion.
- Quotas, rate limits, capacity y performance.
- Budgets, billing reports, rightsizing, autoscaling y cleanup.
- Trade-offs entre costo, latencia, disponibilidad y seguridad.

### 14. Troubleshooting que debe poder resolver

- VM inaccesible por SSH o sin conectividad.
- Firewall bloqueando ingress o egress.
- DNS, rutas, NAT, peering o VPN fallando.
- VM con CPU, memoria o disco saturado.
- Bucket con `403`, `404`, upload fallido o lifecycle incorrecto.
- Cloud SQL sin conexion, permisos, backup o replica.
- Cloud Run o Cloud Functions con deploy fallido, timeout o `5xx`.
- GKE con pods `Pending`, `CrashLoopBackOff`, probes fallando o service sin trafico.
- API deshabilitada, quota agotada, billing suspendido o IAM incorrecto.

### 15. Laboratorios obligatorios

1. Crear una VPC custom con dos subnets.
2. Restringir SSH a la IP propia con una firewall rule.
3. Lanzar una VM, conectarse por SSH e instalar nginx.
4. Crear snapshot y restaurar una VM.
5. Crear bucket, aplicar IAM, lifecycle y versioning.
6. Crear una instancia de Cloud SQL y probar una conexion.
7. Desplegar una Cloud Function y un servicio Cloud Run.
8. Crear una imagen Docker y subirla a Artifact Registry.
9. Crear un deployment y service basicos en GKE.
10. Crear logs, metricas y una alerta.
11. Resolver escenarios de troubleshooting con evidencia.

### 16. Entrevista y soporte

- Explicar conceptos tecnicos en ingles sencillo.
- Hacer preguntas de clarificacion y delimitar el impacto.
- Reproducir, revisar logs, proponer mitigacion y documentar evidencia.
- Distinguir causa, sintoma, workaround y solucion permanente.
- Practicar preguntas orales, escenarios GCP y prueba practica en vivo.
