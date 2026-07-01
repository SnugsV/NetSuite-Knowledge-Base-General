# Pacejet Support Intelligence

## Common Customer Questions

| Question | Domain |
|---|---|
| "The label won't generate." | Label generation |
| "The rate seems too high (or wrong)." | Rate shopping |
| "The tracking number wasn't returned to NetSuite." | Integration update |
| "The carrier isn't showing up in rate results." | Carrier configuration |
| "Pacejet says the connection failed." | API connectivity |
| "The wrong carrier was selected." | Automation rules |
| "The address validation failed." | Address validation |

## Questions to Ask First

1. What carrier and service are you trying to use?
2. What error message are you seeing (exact text)?
3. When did this work last?
4. Were there any recent changes to carrier accounts, Pacejet version, or NetSuite bundle?
5. Is this affecting all shipments or specific ones?
6. Are you seeing this in the Pacejet UI, NetSuite, or both?

## Information Required Before Troubleshooting

- Pacejet version
- NetSuite bundle version
- Carrier name and service level
- Shipment data (item weights, dimensions, addresses)
- Error message text or error code
- System logs (Pacejet API log, NetSuite script log)

## Records to Inspect

| Symptom | Inspect This First |
|---|---|
| Label won't generate | Pacejet error log, carrier contract status, item weight data |
| Rate seems wrong | Carrier contract rates, package dimensions, surcharges |
| Tracking not returned | API log, NetSuite script log, ASD field configuration |
| Carrier not available | Carrier activation status, service level configuration |
| Connection failed | API credentials, network connectivity, Pacejet status page |

## Common Root Causes

| Symptom | Most Likely Causes |
|---|---|
| Label won't generate | 1. Package weight or dimensions missing. 2. Carrier contract expired. 3. Address validation failed. 4. Label connector configuration issue. |
| Wrong rate | 1. Package dimensions incorrect (causing dimensional weight). 2. Wrong carrier contract applied. 3. Fuel surcharge changed. 4. Residential vs. commercial address. |
| Tracking not returned | 1. API callback failed. 2. NetSuite script governance limit reached. 3. ASD field update configuration incorrect. |
| Carrier not showing in rates | 1. Carrier not activated in Pacejet. 2. Service level not configured. 3. Carrier does not serve the origin/destination. |

## Support Conversation Pattern

**Customer says**: "I processed a shipment in Pacejet but the tracking number didn't come back to NetSuite."

**Interpretation**: The Pacejet shipment completed successfully (label generated) but the update back to NetSuite failed. This is typically an API callback issue, a script governance limit, or an ASD field configuration problem.

**Questions to ask**:
- Can you see the shipment in the Pacejet portal with a tracking number?
- Are there errors in the Pacejet API log?
- Are there errors in the NetSuite script execution log?
- Was this a batch shipment or individual?

**Evidence required**: Pacejet shipment confirmation, API log, NetSuite script log.

**Most likely causes**:
1. Pacejet API callback failed (network or authentication)
2. NetSuite script governance limit exceeded
3. ASD field not accepting the tracking number update
4. Scheduled script for status updates not running

**Verification steps**:
1. Check the shipment in the Pacejet portal — confirm it has a tracking number
2. Check the Pacejet API log for callback errors
3. Check NetSuite script execution logs for errors
4. Verify ASD field configuration

**Recommended solution**: Trigger the shipment status update manually or re-run the scheduled script. If recurring, check script governance limits and API callback URL configuration.

## Escalation Criteria

Escalate when:
- Pacejet portal shows an error on the account level
- The NetSuite bundle has a known compatibility issue with the current NetSuite version
- The issue requires Pacejet support to resolve (carrier contract, API credential reset)
- Data integrity issue (corrupted ASD fields, duplicate shipments)
- Integration involves custom SuiteScript beyond the standard bundle

## Related Saved Searches

- Item Fulfillments without tracking numbers
- Shipments by carrier (volume by carrier)
- Failed API calls (from API log)
- ASD field completeness (missing weight or dimensions)
- Shipments by status

## Related Modules

- [Sales](../sales/README.md)
- [Inventory](../inventory/README.md)
- [Administration](../administration/README.md)

## Oracle References

- [Pacejet Knowledge Base](https://pacejet.help.descartesservices.com/)