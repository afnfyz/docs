### Modify Security Groups.

**Open Inbound Ports**

    aws ec2 authorize-security-group-ingress \
    --group-id <security_group_id> \
    --protocol <protocol> \
    --port <port_range> \
    --cidr <cidr_ip_range>

**Close Inbound Ports**
    aws ec2 revoke-security-group-ingress \
    --group-id <security_group_id> \
    --protocol <protocol> \
    --port <port_range> \
    --cidr <cidr_ip_range>

**Open Outbound Ports**

   aws ec2 authorize-security-group-egress \
   --group-id <security_group_id> \
   --protocol <protocol> \
   --port <port_range> \
   --cidr <cidr_ip_range>

**Close Outbound Ports**
    aws ec2 revoke-security-group-egress \
    --group-id <security_group_id> \
    --protocol <protocol> \
    --port <port_range> \
    --cidr <cidr_ip_range>

