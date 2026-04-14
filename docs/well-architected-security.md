# Well-Architected Framework - Security Pillar

## Key Security Decisions

- **S3 Bucket is Private**  
  Block Public Access = ON. No direct public URLs.

- **Origin Access Control (OAC)**  
  Only CloudFront is allowed to read objects from S3.

- **Encryption at Rest**  
  SSE-S3 enabled on the bucket.

- **Encryption in Transit**  
  HTTPS enforced via ACM certificate on CloudFront.

- **Least Privilege**  
  Bucket policy only grants `s3:GetObject` from the specific CloudFront distribution.

## Future Improvements
- Add AWS WAF in front of CloudFront
- Enable S3 Object Lock (if needed)
- Implement logging with CloudTrail + S3 Access Logs

*This project demonstrates core security best practices for static hosting.*


