# Lab 1A – Discussion Questions

## 1. Why does a security log require interpretation?

A security log contains many events, but not all of them indicate malicious activity. Security analysts must interpret the events to determine whether they represent normal behavior or a potential attack.

---

## 2. Why is a detection finding not the same as proof of an attack?

A detection finding only indicates suspicious activity based on predefined rules. Additional investigation is required before confirming that an attack actually occurred.

---

## 3. Why is the original log mounted as read-only?

Mounting the log as read-only protects the original evidence from accidental or intentional modification while allowing the detector to analyze it safely.

---

## 4. What advantages does Docker provide in a physical laboratory?

Docker provides an isolated, consistent, and reproducible environment. Every student runs the same software with the same configuration, reducing setup issues.

---

## 5. How could this detector be improved?

The detector could correlate multiple events, support additional MITRE ATT&CK techniques, reduce false positives, and use configurable detection thresholds.

---

## 6. What additional logs would help confirm brute-force activity?

Useful logs include SSH authentication logs, firewall logs, IDS/IPS alerts, Active Directory authentication logs, and network traffic logs.

---

## 7. What could cause a false positive?

A legitimate administrator repeatedly entering an incorrect password or a vulnerability scanner performing authorized network scans could trigger a detection even though no attack is occurring.

---

## 8. How does MITRE ATT&CK help SOC teams communicate?

MITRE ATT&CK provides a common framework and standardized terminology for describing attacker behavior, making it easier for SOC teams to analyze, report, and discuss security incidents.
