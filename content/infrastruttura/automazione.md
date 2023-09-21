---
title: "Automazione"
date: 2023-04-05T11:33:16+02:00
---

Questa [repository GitHub](https://github.com/csunibo/infrastructure) raccoglie
i file _Ansible_ usati [dalle nostre sistemiste e dai nostri
sistemisti](https://github.com/orgs/csunibo/teams/sistemisti) per manutenere i
nostri servizi. L'infrastruttura sottostante alle macchine virtuali su cui
questi file _Ansible_ vengono eseguiti, invece, è [gestita dalle studentesse e
gli studenti di AdmStaff](https://students.cs.unibo.it/wiki/).

## `bot` ([Informabot](../../bot/informabot))

Per eseguire il playbook sull'host `bot` è necessario inserire il token del bot
di telegram nel file `passwords/bot_token`. Dopo aver messo il bot in esecuzione,
se sono stati aggiunti nuovi comandi è importante
[configurarlo](../../bot/informabot#configurazione)

## `calendar` ([Calendario](../../applicativi-web/calendario))
