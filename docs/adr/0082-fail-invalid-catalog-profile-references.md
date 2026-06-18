# Fail invalid Catalog Profile references

Invalid Catalog Profile references fail catalog validation because profile membership must preserve the centrally curated vocabulary. Treating unknown profile references as warnings or silently omitting them would let plugin manifests introduce semantic drift, weaken profile discovery, and hide catalog governance errors from maintainers.
