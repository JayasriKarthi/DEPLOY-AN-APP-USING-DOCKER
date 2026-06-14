# ⚠️ Troubleshooting

## Error: Docker Command Not Found

Error:

```bash
docker: command not found
```

Solution:

- Restart Docker Desktop
- Restart terminal
- Verify Docker installation

Check:

```bash
docker --version
```

---

## Error: Port 80 Already In Use

Error:

```bash
Bind for 0.0.0.0:80 failed
```

Cause:

Nginx container already running.

Find container:

```bash
docker ps
```

Stop container:

```bash
docker stop CONTAINER_ID
```

Run application again.

---

## Error: Elastic Beanstalk Deployment Failed

Possible causes:

### Incorrect ZIP Structure

Elastic Beanstalk expects:

```text
Dockerfile
index.html
```

inside ZIP root.

---

### Wrong Volume Type

Use:

```text
gp3
```

NOT:

```text
gp2
```

---

### Missing IAM Roles

Verify:

```text
aws-elasticbeanstalk-service-role
```

and

```text
ecsInstanceRole
```

exist.

---

## Error: Cannot Delete S3 Bucket

Cause:

Bucket Policy still exists.

Solution:

```text
S3
→ Bucket
→ Permissions
→ Delete Bucket Policy
```

Then delete bucket.

---