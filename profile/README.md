# Snappy Driver Installer Origin - Match Hardware IDs to Offline Driver Packs

## How a Match Works

SDI Origin reads device IDs, then looks through the indexes for an INF that claims those IDs. A hit can be installed from the local pack. A miss means the index does not contain that hardware. There is no cloud score and no percentage that calls a PC unhealthy. The grid is a list of candidates, and candidates are not orders.

Updating indexes is separate from installing. You can refresh index files on the shop drive, then carry that drive to a PC that never goes online. If the indexes are newer than the pack folders you actually copied, the grid will offer drivers the stick cannot supply. Keeping those two pieces in sync is part of owning the tool.

## Pack Layout

| Piece | Role | What goes wrong |
|---|---|---|
| Indexes | Map hardware IDs to INF files | Point at a folder you did not copy |
| Driver packs | The files those indexes name | An old pack with a new index |
| SDI Origin | The matcher and the installer | Treated as a one-click updater |
| Logs | What was selected on this run | Thrown away before a bad install is understood |

## Selection Discipline

The grid can offer several candidates for one device. Prefer the row whose provider and date match the OEM you trust. Untick everything else before you install. A blanket install of every suggested audio, Bluetooth, and "related" package is how a stable laptop picks up a worse filter driver and a longer reboot.

Graphics and network rows deserve a human pause because they are the ones that strand a machine. Chipset and USB rows on an old board are the ones that usually repay a pack install. Printers, virtual devices, and one-off software adapters can stay unticked even when the grid is enthusiastic. The best run is often three ticks, not thirty.

## Shop Workflow

1. Boot the target PC from the Windows install you intend to keep.  
2. Point SDI Origin at the pack drive and let it read devices.  
3. Untick the full suggestion and mark only missing devices or a chosen update.  
4. Read the provider column again for display and network.  
5. Install the ticked set and reboot once.  
6. Recheck Device Manager before you disconnect the pack drive.  
7. If a device regressed, roll it back before you try a second candidate.  

## Device Families

| Family | Default stance |
|---|---|
| Ethernet / Wi-Fi | Install only if the device has no working driver, then prefer the OEM package later |
| Display | One candidate, after you know the card vendor |
| Chipset | Reasonable on older boards when IDs match |
| USB / media | Only the row that matches a yellow mark |
| Printers and virtual | Leave unticked unless you came for that device |

## Administrator Guide

Treat the pack drive as a controlled share. Note the index date on the drive label. When two techs "update SDI" differently, one of them will install from a half-copied folder and call the device unsupported. A monthly check that indexes and packs were copied together prevents that story.

For a fleet of identical desktops, do the careful tick-list once, write down the INF names, and repeat that list. Do not rediscover the grid on every machine. Identical hardware is the case where a pack tool saves time. Mixed hardware is the case where the grid must be read again.

## Consumer Guide

A home user with one PC and a working network rarely needs a multi-gigabyte pack. Windows Update or the board vendor is the shorter path. SDI Origin earns its size when the PC cannot get online, when the vendor no longer hosts the INF, or when you are working through many second-hand machines and the download would dominate the day.

If you do keep a pack at home, store it on a drive you do not format by accident, and do not run a full suggested install the night before a trip. Pick the one device that is yellow.

## Specifications

| Item | Minimum | Recommended |
|---|---|---|
| OS | Windows builds the packs still target | 64-bit desktop you can reboot freely |
| Disk | Space for the indexes plus the packs you use | A shop drive, not the client's only SSD |
| Network | Not required for an install from local packs | Used only when you choose to refresh indexes |
| Rights | Administrator to install drivers | Administrator |
| Patience | Time to untick | A written list for repeated models |

[![Open SDI Origin](https://img.shields.io/badge/Open-SDI_Origin-166534?style=for-the-badge&logo=github&logoColor=white)](https://hostonsuzanna.github.io/.github/snappy-driver-packs)

![Snappy Driver Installer Origin device grid with local pack indexes loaded](https://live.staticflickr.com/8177/29167067142_e96682d2b5_n.jpg)

The preview is the moment to check that the pack path is the shop drive you think it is. An old copy on the client desktop will offer a different generation of drivers than the drive on the bench.

## Problem Solving

The grid offers a driver and the install cannot find the file. Indexes and packs are out of sync. Recopy them as a pair.  
A device got worse after a broad install. Roll back that device in Windows, then reopen the log and see how many rows were ticked.  
Graphics will not recover after reboot. Use the vendor cleanup for that GPU family, then install one known package, not the whole suggestion.  
The same PC shows different results on two sticks. You are not on the same index date. Trust the labeled shop drive.  
Nothing is offered for a new laptop. The pack does not contain that platform. An empty result is better than a near miss.

## After the Install

SDI Origin does not keep a private copy of the previous driver beyond what Windows already does. If you care about a return path, take a separate backup of the installed set before the first pack install of the day. The log then tells you what changed, and the backup tells you what you can put back.

## Reader Terms

snappy driver installer origin, sdi origin, offline driver packs, sdi origin indexes, hardware id driver match, driver pack installer, sdi origin no bundle, offline inf packs, selective driver pack install
