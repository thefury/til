# Displaying Tags in AWS CLI Output

As names are usually erepresented with tags in AWS, it can be a bit difficult to
print them out in a table. As an example, when creating a listing of VPC names and
IDs, you get the following:


```bash
$ aws ec2 describe-vpcs --query 'Vpcs[*].[Tags[?Key==`Name`].Value, VpcId]' --output table

-------------------
|  DescribeVpcs   |
+-----------------+
|  production     |
|  vpc-aaabbbcc   |
|  poduction2     |
|  vpc-aaabbbcd   |
+-----------------+

```

To fix this, simply add a `|[0]` into the query:

```bash
$ aws ec2 describe-vpcs --query 'Vpcs[*].[Tags[?Key==`Name`]|[0].Value, VpcId]' --output table

-----------------------------------
|          DescribeVpcs           |
+----------------+----------------+
|  production    |  vpc-aaabbbcc  |
|  production2   |  vpc-aaabbbcd  |
+----------------+----------------+

```

