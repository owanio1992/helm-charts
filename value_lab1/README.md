helm dependency update ./value_lab1

helm template test ./value_lab1



global: parent chart 優先
同 Overriding Values

---
# Source: value_lab1/charts/value_lab2/templates/cm.yaml
apiVersion: v1
kind: ConfigMap
metadata:
  name: test-cfgmap2
data:
  dessert: chart1_override
  salad: chart1
---
# Source: value_lab1/templates/cm.yaml
apiVersion: v1
kind: ConfigMap
metadata:
  name: test-cfgmap1
data:
  dessert: chart1
  salad: chart1

