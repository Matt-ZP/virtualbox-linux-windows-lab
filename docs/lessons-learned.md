# Lessons Learned

## Troubleshooting Is a Process

One of the most valuable lessons from this project was that effective troubleshooting is a structured process rather than trial and error.

The most successful investigations followed a repeatable workflow:

1. Identify the symptoms.
2. Gather evidence.
3. Form a hypothesis.
4. Test one change at a time.
5. Verify the outcome.

Changing multiple settings simultaneously makes it difficult to determine the true root cause of a problem.

---

## Documentation Improves Troubleshooting

Maintaining written notes throughout the investigation process made it easier to identify patterns, track changes, and understand how issues were resolved.

Documenting symptoms, investigations, root causes, resolutions, and outcomes created a clear record of the troubleshooting process and provided useful reference material for future projects.

---

## Logs Are Valuable Sources of Evidence

Several issues initially appeared difficult to explain until system logs, service status information, and crash reports were examined.

This project reinforced the importance of gathering evidence before making configuration changes and highlighted the value of logs when diagnosing system behaviour.

---

## Small Configuration Changes Can Have Large Effects

Multiple issues were ultimately caused by relatively small configuration differences, including graphics controller selection, display settings, virtual hardware configuration, and missing Guest Additions dependencies.

This demonstrated how seemingly minor configuration changes can have a significant impact on system stability and usability.

---

## Host and Guest Systems Are Interconnected

Although virtual machines provide isolation from the host operating system, host behaviour can still affect guest systems.

The Ubuntu journald investigation highlighted how interruptions at the host level can influence guest operating system behaviour and stability.

This reinforced the importance of considering the entire environment when troubleshooting.

---

## Virtualisation Provides a Safe Learning Environment

Virtual machines allow experimentation, testing, troubleshooting, and recovery without affecting a production system.

This project demonstrated the value of virtualisation as a platform for developing Linux, Windows, networking, security, and cloud administration skills.

---

## Evidence Collection Can Be Improved

While troubleshooting several issues, I realised that I did not consistently capture screenshots, configuration states, command outputs, or log excerpts throughout the investigation process.

In some cases this made it more difficult to reconstruct the exact troubleshooting sequence after the issue had been resolved.

For future projects I intend to:

* Capture screenshots before and after significant configuration changes.
* Record important command outputs and error messages.
* Save relevant log excerpts during investigations.
* Document configuration settings before modifications are made.
* Maintain a more complete evidence trail throughout the troubleshooting process.

This will improve both troubleshooting accuracy and the quality of technical documentation.

---

## Future Focus Areas

The next stage of development will build upon this foundation by exploring:

* VirtualBox snapshot management and recovery.
* SSH administration and remote access.
* Linux hardening and security configuration.
* Active Directory integration.
* Azure administration and cloud tooling.
* Advanced networking and home lab infrastructure.
* Additional troubleshooting case studies.
