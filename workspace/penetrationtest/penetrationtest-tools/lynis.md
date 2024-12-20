# Lynis Audit Tool

Lynis is a powerful security auditing tool that helps assess the security of Unix-based systems. It performs over 300 checks to identify security issues.

#### Installation and Setup

```bash
mkdir /usr/local/lynis
cd /usr/local/lynis
wget https://cisofy.com/files/lynis-2.2.0.tar.gz
tar -xzf ./lynis-2.2.0.tar.gz
cd lynis
```

#### Running a System Audit

To perform a full system audit:

```bash
./lynis audit system
```

This command runs a comprehensive set of tests and saves the results in `/var/log/lynis-report.dat`.

#### Viewing Audit Results

To view the generated report:

```bash
cat /var/log/lynis-report.dat
```

#### Additional Commands

- To run a specific check:
  ```bash
  ./lynis audit system --check=CHECK_NAME
  ```

- To generate an HTML report:
  ```bash
  ./lynis report generate html /path/to/output/directory
  ```

- To update Lynis to the latest version:
  ```bash
  git pull
  ```

#### Configuration

Lynis can be configured through its configuration file:

```bash
nano /etc/lynis/lynis.conf
```

You can enable or disable specific checks here.

#### Running as Non-root User

By default, some checks require root privileges. You can run Lynis as a non-root user with limited capabilities:

```bash
./lynis audit system --non-root
```

This will perform fewer checks but still provides valuable insights into many aspects of your system's security.

### Best Practices

1. Run Lynis regularly to monitor changes in your system over time.
2. Use the `--report` option to generate reports that can be easily shared or stored for future reference.
3. Pay special attention to high-priority issues identified by Lynis.
4. Address each issue reported by Lynis to improve your system's overall security posture.

Remember to always review the generated report carefully and take appropriate action based on the findings. While Lynis is a powerful tool, it should be used as part of a comprehensive security strategy rather than as the sole method of assessment.

Citations:
[1] https://cisofy.com/documentation/lynis/get-started/
[2] https://cisofy.com/documentation/lynis/
[3] https://www.youtube.com/watch?v=fUIpJJn6YaM
[4] https://www.digitalocean.com/community/tutorials/how-to-perform-security-audits-with-lynis-on-ubuntu-16-04
[5] https://www.tecmint.com/linux-security-auditing-and-scanning-with-lynis-tool/
[6] https://cisofy.com/lynis/
[7] https://www.linode.com/docs/guides/security-auditing-with-lynis/
[8] https://www.reddit.com/r/linuxquestions/comments/1czzovy/problem_installing_and_running_lynis_audit_system/
[9] https://linuxsecurity.expert/training/modules/guides/installation-and-configuration-of-lynis
[10] https://www.geeksforgeeks.org/lynis-security-tool-for-audit-and-hardening-linux-systems/