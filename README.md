# Máquinas — Write-ups de Pentesting

Repositorio con los write-ups de las máquinas vulnerables que he ido resolviendo como parte de mi preparación en ciberseguridad ofensiva (eJPT y práctica continua). Cada write-up documenta la metodología completa: reconocimiento, explotación, escalada de privilegios y flags/objetivos conseguidos.

## 🗂️ Índice de máquinas

### DockerLabs

| Máquina | SO | Resumen | Write-up |
|---|---|---|---|
| Backend | Linux | Inyección SQL con sqlmap para volcar credenciales y acceso por SSH | [Ver write-up](dockerlabs/backend/writeup.md) |
| FindYourStyle | Linux | Explotación de Drupal (CVE-2018-7600) y escalada vía binario `su` | [Ver write-up](dockerlabs/find-your-style/writeup.md) |
| Library | Linux | Python Library Hijacking para escalar a root | [Ver write-up](dockerlabs/library/writeup.md) |
| Mirame | Linux | Bypass de autenticación, inyección SQL, esteganografía (steghide/stegseek) y GTFOBins | [Ver write-up](dockerlabs/mirame/writeup.md) |
| hannah_coffee | Linux | LFI + FTP Log Poisoning para RCE, escalada con sudo y capabilities | [Ver write-up](dockerlabs/hannah-coffee/writeup.md) |
| Trust | Linux | Fuerza bruta SSH con hydra y escalada abusando de vim con sudo (GTFOBins) | [Ver write-up](dockerlabs/trust/writeup.md) |
| BreakMySSH | Linux | Enumeración de usuarios SSH desde Metasploit y fuerza bruta con hydra | [Ver write-up](dockerlabs/breakmyssh/writeup.md) |
| AnonymousPingu | Linux | FTP anónimo con subida de reverse shell PHP y escalada encadenada (GTFOBins) | [Ver write-up](dockerlabs/anonymouspingu/writeup.md) |
| Dance-Samba | Linux | Enumeración SMB, fuerza bruta con Metasploit, SSH Key Injection y escalada encontrando credenciales de root | [Ver write-up](dockerlabs/dance-samba/writeup.md) |
| Domain | Linux | Enumeración SMB (rpcclient, smbmap), fuerza bruta con netexec, reverse shell PHP y escalada abusando de nano con sudo (GTFOBins) | [Ver write-up](dockerlabs/domain/writeup.md) |
| Vulnerame | Linux | Explotación de Joomla vulnerable, dump de credenciales vía MySQL, RCE por plantilla de administrador y escalada abusando de un script Ruby con sudo | [Ver write-up](dockerlabs/vulnerame/writeup.md) |

### TryHackMe

_Pendiente de migrar._

## 📁 Estructura del repositorio

```
maquinas-writeups/
├── README.md
├── machines.json              ← datos estructurados (para consumir desde la web)
├── dockerlabs/
│   └── nombre-maquina/
│       ├── writeup.md
│       └── screenshots/
└── tryhackme/
    └── nombre-maquina/
        ├── writeup.md
        └── screenshots/
```

## 📝 Formato de cada write-up

Cada `writeup.md` sigue esta estructura:

1. **Información general** — plataforma, dificultad, SO, IP
2. **Reconocimiento** — escaneo de puertos, servicios detectados, enumeración
3. **Explotación** — vulnerabilidad encontrada y cómo se explota
4. **Escalada de privilegios** — camino hasta root/administrator
5. **Flags / Objetivos** — capturas conseguidas
6. **Lecciones aprendidas** — takeaways técnicos relevantes para el eJPT

## 🎯 Sobre este repositorio

Este repositorio forma parte de mi portfolio de ciberseguridad, junto con mis herramientas JGScan, JGSAnalyzer y JGSPasswordKeys. Los contenidos se integran también en la sección **Laboratorio de ciberseguridad** de mi web de portfolio.

## ⚠️ Disclaimer

Todas las máquinas resueltas pertenecen a plataformas legales de práctica (DockerLabs, TryHackMe) diseñadas específicamente para entrenamiento en ciberseguridad ofensiva. Ningún contenido de este repositorio debe usarse contra sistemas sin autorización explícita.