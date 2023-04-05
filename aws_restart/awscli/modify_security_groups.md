### Modify Security Groups.

**Inbound Rules**

    aws ec2 authorize-security-group-ingress \
    --group-id <security_group_id> \
    --protocol <protocol> \
    --port <port_range> \
    --cidr <cidr_ip_range>

**Outbound Rules**

   aws ec2 authorize-security-group-egress \
   --group-id <security_group_id> \
   --protocol <protocol> \
   --port <port_range> \
   --cidr <cidr_ip_range>

