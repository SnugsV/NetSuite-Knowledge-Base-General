# Source Registry

## Purpose

All monitored vendor sources. This registry defines what to monitor, where to find it, and how to detect changes.

## Oracle NetSuite

| Source | URL / Location | Change Detection Method |
|---|---|---|
| Release Notes | https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/ | Check for new version numbers |
| Help Center | https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/ | Check for new or updated topics |
| SuiteAnswers | https://suiteanswers.custhelp.com/ | Check for new articles |
| SuiteScript Documentation | https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/ | Check for API changes |
| REST API Documentation | https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/ | Check for endpoint changes |
| Record Browser | https://system.netsuite.com/app/help/help.nl | Check for field changes |

## Descartes / Pacejet

| Source | URL / Location | Change Detection Method |
|---|---|---|
| Pacejet Help Center | https://pacejet.help.descartesservices.com/ | RSS feed or page diff |
| Release Notes (Shipping) | KB page: Pacejet Shipping | Check for new notes |
| Release Notes (Connector) | KB page: Pacejet Connector | Check for new bundle versions |
| Release Notes (Scale/Cubiscan) | KB page: Pacejet Scale/Cubiscan | Check for new versions |
| Carrier Updates | KB page: Carriers | Check carrier-specific notes |

## Future Sources

| Source | URL / Location | Status |
|---|---|---|
| Avalara Documentation | https://help.avalara.com/ | Not yet monitored |
| Celigo Documentation | https://docs.celigo.com/ | Not yet monitored |
| RF-SMART Documentation | https://help.rfsmart.com/ | Not yet monitored |
| SPS Commerce | https://www.spscommerce.com/resources/ | Not yet monitored |
| Shopify API Changelog | https://shopify.dev/changelog | Not yet monitored |
| HubSpot Release Notes | https://community.hubspot.com/ | Not yet monitored |
| Salesforce Release Notes | https://help.salesforce.com/ | Not yet monitored |

## Registry Maintenance

- Add new sources as integrations are documented
- Update URLs when sources change
- Archive sources that are no longer maintained
- Review registry quarterly for accuracy