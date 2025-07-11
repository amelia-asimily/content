Dynamically retrieve and allow IPs Prisma Access uses to egress traffic to the internet and SaaS apps.

## Configure Prisma Access Egress IP feed in Cortex

| **Parameter** | **Description** | **Required** |
| --- | --- | --- |
| feed | Fetch indicators | False |
| URL | URL | True |
| api_key | Prisma Access API Key from Panorama | True |
| serviceType | Service Type | True |
| addrType | Address Type | True |
| location | Location | False |
| feedReputation | Indicator Reputation | False |
| feedReliability | Source Reliability | True |
| tlp_color | The Traffic Light Protocol (TLP) designation to apply to indicators fetched from the feed. More information about the protocol can be found at https://us-cert.cisa.gov/tlp | False |
| feedExpirationPolicy |  | False |
| feedExpirationInterval |  | False |
| feedFetchInterval | Feed Fetch Interval | False |
| feedBypassExclusionList | Bypass exclusion list | False |
| insecure | Trust any certificate \(not secure\) | False |
| proxy | Use system proxy settings | False |

## Retrieve Egress API Key

To retrieve the Egress API key from Panorama - Click "Generate API Key" under **Panorama->Cloud Services->Configuration->Service Setup.** For more information, see [Retrieve the IP Addresses for Prisma Access](https://docs.paloaltonetworks.com/prisma/prisma-access/prisma-access-panorama-admin/prisma-access-overview/retrieve-ip-addresses-for-prisma-access).

## Commands

You can execute these commands from the CLI, as part of an automation, or in a playbook.
After you successfully execute a command, a DBot message appears in the War Room with the command details.

### prisma-access-get-indicators

***
Gets indicators from the feed.

##### Base Command

`prisma-access-get-indicators`

##### Input

| **Argument Name** | **Description** | **Required** |
| --- | --- | --- |
| limit | The maximum number of results to return.  By default all IPs are returned. | Optional |

##### Context Output

| **Path** | **Type** | **Description** |
| --- | --- | --- |
| PrismaAccess.Egress.IP.Address | string | Prisma Access Egress IP address |
| PrismaAccess.Egress.IP.Zone | string | Prisma Access Egress IP zone |

##### Command Example

```!prisma-access-get-indicators limit=300```
