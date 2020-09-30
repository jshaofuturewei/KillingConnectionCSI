

### Common Test Setup (specify specific test change below )

- 5000 nodes
- Load test only
- WCM disabled
- Perf-test tool: https://github.com/sonyafenge/perf-tests.git
- ETCD 3.4.3
- Leader-election disabled
- Coredump enabled
- Insecure-port enabled
- Prometheus enabled

### Build Date: 06/10 No fail


### Build Date: 06/12 No fail
date of run:


### Build Date: 06/18

- Commit: 91f3f2bb1d89038223264eb246552e856559c050

- Runner: Joe

- Date of run: Sep 30

- Environment: export MASTER_DISK_SIZE=1000GB MASTER_ROOT_DISK_SIZE=1000GB KUBE_GCE_ZONE=us-west2-b MASTER_SIZE=n1-highmem-96 NODE_SIZE=n1-highmem-16 NUM_NODES=55 NODE_DISK_SIZE=1000GB GOPATH=$HOME/go KUBE_GCE_ENABLE_IP_ALIASES=true KUBE_GCE_PRIVATE_CLUSTER=true CREATE_CUSTOM_NETWORK=true KUBE_GCE_INSTANCE_PREFIX=node5000-0618  KUBE_GCE_NETWORK=node5000-0618   ETCD_QUOTA_BACKEND_BYTES=8589934592 TEST_CLUSTER_LOG_LEVEL=--v=2  SHARE_PARTITIONSERVER=true APISERVERS_EXTRA_NUM=0 WORKLOADCONTROLLER_EXTRA_NUM=0 ETCD_EXTRA_NUM=0 LOGROTATE_FILES_MAX_COUNT=10 LOGROTATE_MAX_SIZE=200M KUBEMARK_NUM_NODES=5000


- Command: GOPATH=$HOME/go nohup ./clusterloader2/run-e2e.sh --nodes=5000 --provider=kubemark --kubeconfig=/home/sonyali/go/src/k8s.io/arktos/test/kubemark/resources/kubeconfig.kubemark --report-dir=/home/sonyali/logs/perf-test/gce-5000/arktos/0929-0618 --testconfig=testing/density/config.yaml


- Result: 
  - Many  Kube-apiserver panics. “killing connection/stream”
  -  The load test completed with 1 failure that many objects got timed out as usual
  - Not many “took too long” warning of “registry/leases/kube-node-lease/hollow-node” as usual. There are only 2712 out of the 38294 “took too long” warnings. It used to be more than 80%.
  - There are many context canceled errors in the etcd.log
  - Log: jundev2:/home/shaoj9/logs/perf-test/gce-5000/arktos/0929-0618-91f3



### Build Date: 06/25

- Commit: ???

- Runner: Vinay

- Date of run:

- Result: 
  -  load test completed with timeouts. No panic or killing connection logs.

---

- Commit: ???

- Runner: Joe

- Date of run:

- Result: 
  -  N/A


### Build Date: 09/24

- Commit: 40fd8c82fbd0446c2bf32a558004849335025120

- Runner: Sonya

- Date of run:

- Result: 
  - Kube-apiserver Panic: killing connection/stream
  - Perf-tests tool panic: runtime error: invalid memory address or nil pointer dereference
  - logs can be found under GCP project: workload-controller-manager on sonya-useast1: /home/sonyali/logs/perf-test/gce-5000/arktos/0929-communityperf-1a0w1e
  - Prometheus report can be found at [http://35.231.121.60:9090/](https://nam11.safelinks.protection.outlook.com/?url=http%3A%2F%2F35.231.121.60%3A9090%2F&data=02|01|peng.du%40futurewei.com|50f8201d0df9413f5dbf08d865752edb|0fee8ff2a3b240189c753a1d5591fedc|1|0|637370901289650492&sdata=uINL%2B1heyhSHkiGabpRKXAXtUwaE6Nstz0qmVzd24Sc%3D&reserved=0) or snapshot can be found on sonya-useast1: /home/sonyali/logs/perf-test/gce-5000/arktos/0929-communityperf-1a0w1e/logs/crashed/kubemarkmaster/prometheus/snapshots

 



