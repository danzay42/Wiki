---
tags: OSI
title: 
	- Сетевая модель
	- The Open Systems Interconnection model
aliases: 
date: 2023-11-04
---


# Сетевая модель 

|               |              |        |                             |
| ------------- | ------------ | ------ | --------------------------- |
| прикладной    | application  | данные | HTTP, FTP, WebSocket                        |
| представления | presentation | данные | SSL                            |
| сеансовый     | session      | данные | RPC, gRPC                   |
| транспортный  | transport    | блоки  | TCP, UDP, sockets (ip:port) |
| сетевой       | network      | пакеты | IPv4, ipv6                 |
| канальный     | data link    | кадры  | MAC / LLC, arp              |
| физический    | physical     | биты   | физические сигналы          |
