# Unknown "Warning Group" Warnings (`unknown_warning_group`)

The `unknown_warning_group` diagnostic group addresses warnings related to the specification of unrecognized warning groups in compilation flags.

```sh
swiftc -warning-as-error non_existing_group file.swift
<unknown>:0: warning: unknown warning group: 'non_existing_group'
```

Such warnings are emitted after the behavior for all specified warning groups has been processed, which means their behavior can also be specified. For example:

```sh
swiftc -warning-as-error unknown_warning_group -warning-as-error non_existing_group file.swift
<unknown>:0: error: unknown warning group: 'non_existing_group'
```
