# Local edits to Frappe and ERPNext core

`apps/frappe` and `apps/erpnext` are upstream checkouts, so these edits cannot be
pushed there. They are kept here so they can be re-applied after a fresh clone or update:

```bash
git -C apps/frappe apply ../../core-patches/frappe.patch
git -C apps/erpnext apply ../../core-patches/erpnext.patch
```

- `frappe.patch`: compatibility shims for the Frappe/ERPNext develop versions in use
  (`Meta.get_translated_label`, recursive CTE query builder, `savedocs` null guard,
  sidebar workspace filter).
- `erpnext.patch`: matching JS/import shims, the Supplier Scorecard `criteria` guard
  needed because apparel_track replaces that DocType, and the Buying workspace JSON.
