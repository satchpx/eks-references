# Security Group for Pods

## Example 1: Block a green-pod from communicating with any other pod, but reach out to internet
Step 1: Create a network policy that denies all traffic to other pods within the EKS cluster
```
kubectl apply -f network-policy.yaml
```

Step 2: Create a security group for the pod that allows outbound traffic to the internet in the VPC associated with your EKS cluster.

Step 3: Create a SecurityGroup Policy
```
kubectl apply -f sg-policy.yaml
```
This policy references the Security Group created in step 2

Step 4: Create a test pod
```
kubectl apply -f pod.yaml
```