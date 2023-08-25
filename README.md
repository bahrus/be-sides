# be-sides [TODO]

*be-sides* allows one HTML signal (itemprop) to affect (and create) other computed HTML signals. 

```html
<link itemprop=prop1  be-sides='
    Negate to prop2.
' href=https://schema.org/True>
```

generates:

```html
<link itemprop=prop1  be-sides='
    Negate to prop2.
' href=https://schema.org/True>
<link itemprop=prop2 href=https://schema.org/False>
```

Other actions:

| Action     | What it does                      |
|------------|-----------------------------------|
| toggleTo   | toggles peer itemprop to opposite |
| dispatch   | fires event from host             |

etc (copied from xtal-element/types.d.ts)

Lots of (potential) examples:

```html
<link itemprop=prop1  be-sides='
    Negate to prop2.
    Negate to prop2 after 40 ms.
    Toggle to prop2.
    Toggle to prop2 after 40 ms.
    Echo to prop2.
    Echo to prop2 after 40 ms.
    Reflect to host attr.
    Reflect to host custom state.
    Parse to prop2 as number.
    Parse to prop2 as date.
    Parse to prop2 as object.
    Dispatch.
    Clone to prop2.
    Increment to prop2. //Use be counted on target element to specify particulars
' href=https://schema.org/True>
```