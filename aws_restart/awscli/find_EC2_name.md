### Get the name of EC2 instance once you have it's ID.
   
    EC2_NAME=$(aws ec2 describe-tags \
    --region us-west-2 \
    --filters "Name=resource-id Values=i-022bf52d928885ea4" "Name=key,Values=Name" --output text | cut -f5)