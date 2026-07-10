# SPS Commerce Integration

This module covers SPS Commerce as an EDI and retail supply-chain integration platform connected with NetSuite order, shipment, invoice, item, and trading partner workflows.

## Learning Path

| Step | Article | Est. Time | Topic |
|---|---|---:|---|
| 1 | [Advanced Troubleshooting](advanced-troubleshooting.md) | 20 min | EDI lifecycle, PO acknowledgments, ASNs, invoices, mappings, connector and portal errors |
| 2 | [Bulk Purchase Order Acknowledgment Workflow](sps-bulk-po-acknowledgment-workflow.md) | 15 min | Bulk EDI 855 processing from eligible NetSuite sales orders |
| 3 | [Bulk ASN Workflow](sps-bulk-asn-workflow.md) | 15 min | Bulk EDI 856 processing from shipped NetSuite item fulfillments |
| - | **Estimated total time** | **50 min** | - |

## How SPS Commerce Connects

| NetSuite Area | SPS Commerce Connection |
|---|---|
| **Sales Orders** | Inbound purchase orders and order changes from trading partners |
| **Fulfillment** | Shipment data, ASN/856 documents, routing, carton, and tracking details |
| **Invoicing** | Outbound invoice/810 documents and mismatch resolution |
| **Items** | Item identifiers, UPCs, partner SKUs, case packs, units of measure, and catalog data |
| **Customers/Partners** | Trading partner requirements, ship-to locations, routing rules, and compliance expectations |

## Public-Safe Rule

Keep examples generic. Do not include retailer names tied to private requirements, customer data, purchase order numbers, invoice numbers, shipment identifiers, trading partner IDs, VAN/mailbox credentials, EDI maps, production logs, screenshots, pricing, or private operating procedures.

## Related Modules

- [Sales](../../sales/README.md)
- [Inventory](../../inventory/README.md)
- [Accounting](../../accounting/README.md)
- [Advanced NetSuite Troubleshooting](../../advanced-troubleshooting/README.md)

## Public References

- [SPS Commerce](https://www.spscommerce.com/)
- SPS Commerce EDI and Fulfillment product information
- SPS Commerce customer support and training resources
