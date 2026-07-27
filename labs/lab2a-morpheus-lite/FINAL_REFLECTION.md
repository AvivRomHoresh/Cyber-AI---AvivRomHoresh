# Lab 2A – Morpheus Lite
## Final Reflection

### Selected Case Information

- **Alert ID:** `alert-0-1035`
- **Risk Score:** `80`
- **User:** `svc-backup`
- **Host:** `host-01`
- **Event Type:** `http_request`
- **Fingerprint Deviation:** `141.3506`
- **Inference Provider:** `ollama`
- **RAI Recommended Action:** `increase_monitoring`
- **Human Decision:** `approve`

---

## 1. Which evidence most influenced your decision?

**Answer:**

The evidence that most influenced my decision was the user-specific fingerprint deviation with a z-score of `141.3506`.

This value indicates that the behavior associated with the `svc-backup` account was significantly different from its historical behavioral profile. The deviation was therefore strong enough to justify additional attention and monitoring.

However, this was also the only direct evidence presented in the case. There was no supporting evidence of suspicious authentication activity, malicious process execution, unusual outbound network traffic, privilege escalation, or confirmed data exfiltration.

For this reason, the evidence supported increased monitoring, but it did not justify an immediate disruptive response.

---

## 2. Did your decision agree with the AI recommendation? Why or why not?

**Answer:**

My decision was:

`approve`

The RAI recommendation was:

`increase_monitoring`

My decision agreed with the AI recommendation because increased monitoring was a proportionate response to the available evidence.

The alert showed a significant behavioral deviation, but the current evidence did not independently confirm malicious activity. Approving increased monitoring allowed the system and the human analyst to continue gathering evidence without unnecessarily blocking the account, isolating the host, or disrupting a legitimate service.

Therefore, I approved the recommendation to increase monitoring only. I did not approve any destructive or restrictive action.

---

## 3. Did the RAI policy meaningfully constrain the action?

**Answer:**

The RAI policy returned the following decision:

- **Allowed:** `true`
- **Recommended Action:** `increase_monitoring`
- **Human Approval Required:** `false`
- **Policy Evidence Count:** `1`
- **Policy Note:**  
  `Medium risk. Automated destructive actions are blocked.`

The RAI policy meaningfully constrained the action because it allowed only a low-impact and reversible response.

Although the risk score was `80`, the case was supported by only one behavioral indicator. The policy therefore prevented automated destructive actions such as disabling the account, blocking the user, isolating the host, or terminating a service.

This constraint was appropriate because the available evidence showed an anomaly but did not confirm that the activity was malicious. The RAI policy reduced the risk of causing operational damage based on incomplete evidence.

---

## 4. Did the Meta-AI review identify uncertainty or challenge the recommendation?

**Answer:**

The Meta-AI review returned:

- **Approved:** `true`
- **Disposition:** `approve`
- **Uncertainty:** `0.2`
- **Issues:** `None`
- **Questions or Requests:** `None`
- **Reflection:**  
  `Decision is sufficiently supported for governed continuation.`

The Meta-AI review mostly confirmed the recommendation rather than critically challenging it.

It approved the RAI decision and did not identify any issues or request additional evidence. However, the XAI explanation itself stated that the intent and severity of the anomaly were unclear and that further investigation was required.

The Meta-AI review did not challenge the fact that the case relied on only one piece of evidence. It also did not question the speculative MITRE ATT&CK interpretation involving Credential Access, Exfiltration, and Privilege Escalation.

Therefore, the Meta-AI review provided supervisory approval, but it did not perform a strong critical examination of the weaknesses and limitations of the evidence.

---

## 5. What additional evidence would have changed your decision?

**Answer:**

The following additional evidence could have changed my decision:

- Multiple failed login attempts associated with the account
- Authentication from an unusual country, device, or source IP address
- Execution of a suspicious or unauthorized process
- Abnormally large outbound data transfers
- Evidence of unauthorized privilege escalation
- Endpoint Detection and Response alerts
- Suspicious commands executed by the service account
- Access to systems or files that are not normally used by `svc-backup`
- Correlated alerts from other users, hosts, or network devices

If several of these indicators had appeared together, I might have selected `escalate` or requested immediate containment.

On the other hand, evidence showing that the deviation was caused by a legitimate backup operation, maintenance task, software update, or approved configuration change could have reduced the severity of the alert and supported closing or deferring the case.

---

## 6. At what point in the pipeline should human authority be strongest?

**Answer:**

Human authority should be strongest before response execution, especially before any disruptive, destructive, or irreversible action is performed.

The automated pipeline can generate telemetry, detect anomalies, explain findings, apply policy rules, and provide recommendations. However, a human analyst should retain final authority before actions such as:

- Disabling a user account
- Blocking network access
- Isolating a host
- Terminating a process
- Stopping a business service
- Deleting or modifying data
- Escalating the incident to external parties

AI systems may rely on incomplete data, generate incorrect interpretations, or overestimate the severity of an anomaly. A human analyst can consider business context, operational impact, policy requirements, and evidence that may not be available to the automated system.

In this case, the human decision was important because the alert was based on a strong deviation but lacked evidence confirming malicious activity.

---

## 7. What are the risks of automatically executing the recommended action?

**Answer:**

Automatically executing an AI recommendation may create several risks:

- False-positive containment
- Disruption of legitimate business activity
- Locking a legitimate service account
- Interrupting backup or maintenance operations
- Loss of system or service availability
- Actions based on incomplete or misleading evidence
- Incorrect interpretation of normal behavior as malicious
- Excessive reliance on AI-generated explanations
- Failure to consider organizational or operational context
- Difficulty reversing an automated destructive action

In this case, automatically applying a destructive response based only on the fingerprint deviation could have interrupted a legitimate backup service.

The actual RAI recommendation was to increase monitoring, which is relatively safe and reversible. However, more aggressive actions should not be executed automatically without additional evidence and human approval.

