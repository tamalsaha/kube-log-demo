# kube-log-demo

## Demo Projects

- https://github.com/tamalsaha/std-log-demo
- https://github.com/tamalsaha/glog-demo
- https://github.com/tamalsaha/kube-log-demo
- https://github.com/tamalsaha/ac-log-demo

```console
$ kube-log-demo check -h
Check restic backup

Usage:
   check [flags]

Flags:
  -h, --help                help for check
      --kubeconfig string   Path to kubeconfig file with authorization information (the master location is set by the master flag).
      --master string       The address of the Kubernetes API server (overrides any value in kubeconfig)

Global Flags:
      --alsologtostderr                  log to standard error as well as files
      --analytics                        Send analytical events to Google Analytics (default true)
      --log_backtrace_at traceLocation   when logging hits line file:N, emit a stack trace (default :0)
      --log_dir string                   If non-empty, write log files in this directory
      --logtostderr                      log to standard error instead of files
      --stderrthreshold severity         logs at or above this threshold go to stderr (default 2)
  -v, --v Level                          log level for V logs
      --vmodule moduleSpec               comma-separated list of pattern=N settings for file-filtered logging

$ kube-log-demo check --kubeconfig=/home/tamal/.kube/config
2018/01/08 18:33:58 FLAG: --alsologtostderr="false"
2018/01/08 18:33:58 FLAG: --analytics="true"
2018/01/08 18:33:58 FLAG: --help="false"
2018/01/08 18:33:58 FLAG: --kubeconfig="/home/tamal/.kube/config"
2018/01/08 18:33:58 FLAG: --log_backtrace_at=":0"
2018/01/08 18:33:58 FLAG: --log_dir=""
2018/01/08 18:33:58 FLAG: --logtostderr="false"
2018/01/08 18:33:58 FLAG: --master=""
2018/01/08 18:33:58 FLAG: --stderrthreshold="2"
2018/01/08 18:33:58 FLAG: --v="0"
2018/01/08 18:33:58 FLAG: --vmodule=""
log.Println_____
2018/01/08 18:33:58 minikube
glog.Infoln_____
glog.Warningln_____
glog.Errorln_____
E0108 18:33:58.610181   16765 main.go:70] minikube
glog.V(0).Infoln_____
glog.V(1).Infoln_____
glog.V(2).Infoln_____
glog.V(3).Infoln_____
glog.V(4).Infoln_____

$ kube-log-demo check --kubeconfig=/home/tamal/.kube/config --v=2
2018/01/08 18:34:05 FLAG: --alsologtostderr="false"
2018/01/08 18:34:05 FLAG: --analytics="true"
2018/01/08 18:34:05 FLAG: --help="false"
2018/01/08 18:34:05 FLAG: --kubeconfig="/home/tamal/.kube/config"
2018/01/08 18:34:05 FLAG: --log_backtrace_at=":0"
2018/01/08 18:34:05 FLAG: --log_dir=""
2018/01/08 18:34:05 FLAG: --logtostderr="false"
2018/01/08 18:34:05 FLAG: --master=""
2018/01/08 18:34:05 FLAG: --stderrthreshold="2"
2018/01/08 18:34:05 FLAG: --v="2"
2018/01/08 18:34:05 FLAG: --vmodule=""
log.Println_____
2018/01/08 18:34:05 minikube
glog.Infoln_____
glog.Warningln_____
glog.Errorln_____
E0108 18:34:05.920840   16829 main.go:70] minikube
glog.V(0).Infoln_____
glog.V(1).Infoln_____
glog.V(2).Infoln_____
glog.V(3).Infoln_____
glog.V(4).Infoln_____

$ kube-log-demo check --kubeconfig=/home/tamal/.kube/config --v=2 --logtostderr=true
2018/01/08 18:34:17 FLAG: --alsologtostderr="false"
2018/01/08 18:34:17 FLAG: --analytics="true"
2018/01/08 18:34:17 FLAG: --help="false"
2018/01/08 18:34:17 FLAG: --kubeconfig="/home/tamal/.kube/config"
2018/01/08 18:34:17 FLAG: --log_backtrace_at=":0"
2018/01/08 18:34:17 FLAG: --log_dir=""
2018/01/08 18:34:17 FLAG: --logtostderr="true"
2018/01/08 18:34:17 FLAG: --master=""
2018/01/08 18:34:17 FLAG: --stderrthreshold="2"
2018/01/08 18:34:17 FLAG: --v="2"
2018/01/08 18:34:17 FLAG: --vmodule=""
log.Println_____
2018/01/08 18:34:17 minikube
glog.Infoln_____
I0108 18:34:17.592565   16889 main.go:64] minikube
glog.Warningln_____
W0108 18:34:17.592578   16889 main.go:67] minikube
glog.Errorln_____
E0108 18:34:17.592587   16889 main.go:70] minikube
glog.V(0).Infoln_____
I0108 18:34:17.592596   16889 main.go:75] minikube
glog.V(1).Infoln_____
I0108 18:34:17.592605   16889 main.go:78] minikube
glog.V(2).Infoln_____
I0108 18:34:17.592613   16889 main.go:81] minikube
glog.V(3).Infoln_____
glog.V(4).Infoln_____

$ kube-log-demo check --kubeconfig=/home/tamal/.kube/config --logtostderr=true
2018/01/08 18:34:25 FLAG: --alsologtostderr="false"
2018/01/08 18:34:25 FLAG: --analytics="true"
2018/01/08 18:34:25 FLAG: --help="false"
2018/01/08 18:34:25 FLAG: --kubeconfig="/home/tamal/.kube/config"
2018/01/08 18:34:25 FLAG: --log_backtrace_at=":0"
2018/01/08 18:34:25 FLAG: --log_dir=""
2018/01/08 18:34:25 FLAG: --logtostderr="true"
2018/01/08 18:34:25 FLAG: --master=""
2018/01/08 18:34:25 FLAG: --stderrthreshold="2"
2018/01/08 18:34:25 FLAG: --v="0"
2018/01/08 18:34:25 FLAG: --vmodule=""
log.Println_____
2018/01/08 18:34:25 minikube
glog.Infoln_____
I0108 18:34:25.759990   16932 main.go:64] minikube
glog.Warningln_____
W0108 18:34:25.760027   16932 main.go:67] minikube
glog.Errorln_____
E0108 18:34:25.760049   16932 main.go:70] minikube
glog.V(0).Infoln_____
I0108 18:34:25.760072   16932 main.go:75] minikube
glog.V(1).Infoln_____
glog.V(2).Infoln_____
glog.V(3).Infoln_____
glog.V(4).Infoln_____

$ kube-log-demo check --kubeconfig=/home/tamal/.kube/config --logtostderr=true --stderrthreshold=1
2018/01/08 18:34:49 FLAG: --alsologtostderr="false"
2018/01/08 18:34:49 FLAG: --analytics="true"
2018/01/08 18:34:49 FLAG: --help="false"
2018/01/08 18:34:49 FLAG: --kubeconfig="/home/tamal/.kube/config"
2018/01/08 18:34:49 FLAG: --log_backtrace_at=":0"
2018/01/08 18:34:49 FLAG: --log_dir=""
2018/01/08 18:34:49 FLAG: --logtostderr="true"
2018/01/08 18:34:49 FLAG: --master=""
2018/01/08 18:34:49 FLAG: --stderrthreshold="1"
2018/01/08 18:34:49 FLAG: --v="0"
2018/01/08 18:34:49 FLAG: --vmodule=""
log.Println_____
2018/01/08 18:34:49 minikube
glog.Infoln_____
I0108 18:34:49.592019   17033 main.go:64] minikube
glog.Warningln_____
W0108 18:34:49.592040   17033 main.go:67] minikube
glog.Errorln_____
E0108 18:34:49.592057   17033 main.go:70] minikube
glog.V(0).Infoln_____
I0108 18:34:49.592073   17033 main.go:75] minikube
glog.V(1).Infoln_____
glog.V(2).Infoln_____
glog.V(3).Infoln_____
glog.V(4).Infoln_____

$ kube-log-demo check --kubeconfig=/home/tamal/.kube/config --logtostderr=true --stderrthreshold=1 --v=1
2018/01/08 18:34:55 FLAG: --alsologtostderr="false"
2018/01/08 18:34:55 FLAG: --analytics="true"
2018/01/08 18:34:55 FLAG: --help="false"
2018/01/08 18:34:55 FLAG: --kubeconfig="/home/tamal/.kube/config"
2018/01/08 18:34:55 FLAG: --log_backtrace_at=":0"
2018/01/08 18:34:55 FLAG: --log_dir=""
2018/01/08 18:34:55 FLAG: --logtostderr="true"
2018/01/08 18:34:55 FLAG: --master=""
2018/01/08 18:34:55 FLAG: --stderrthreshold="1"
2018/01/08 18:34:55 FLAG: --v="1"
2018/01/08 18:34:55 FLAG: --vmodule=""
log.Println_____
2018/01/08 18:34:55 minikube
glog.Infoln_____
I0108 18:34:55.289093   17081 main.go:64] minikube
glog.Warningln_____
W0108 18:34:55.289107   17081 main.go:67] minikube
glog.Errorln_____
E0108 18:34:55.289115   17081 main.go:70] minikube
glog.V(0).Infoln_____
I0108 18:34:55.289125   17081 main.go:75] minikube
glog.V(1).Infoln_____
I0108 18:34:55.289133   17081 main.go:78] minikube
glog.V(2).Infoln_____
glog.V(3).Infoln_____
glog.V(4).Infoln_____

$ kube-log-demo check --kubeconfig=/home/tamal/.kube/config --logtostderr=true --stderrthreshold=1 --v=2
2018/01/08 18:35:00 FLAG: --alsologtostderr="false"
2018/01/08 18:35:00 FLAG: --analytics="true"
2018/01/08 18:35:00 FLAG: --help="false"
2018/01/08 18:35:00 FLAG: --kubeconfig="/home/tamal/.kube/config"
2018/01/08 18:35:00 FLAG: --log_backtrace_at=":0"
2018/01/08 18:35:00 FLAG: --log_dir=""
2018/01/08 18:35:00 FLAG: --logtostderr="true"
2018/01/08 18:35:00 FLAG: --master=""
2018/01/08 18:35:00 FLAG: --stderrthreshold="1"
2018/01/08 18:35:00 FLAG: --v="2"
2018/01/08 18:35:00 FLAG: --vmodule=""
log.Println_____
2018/01/08 18:35:00 minikube
glog.Infoln_____
I0108 18:35:00.951164   17115 main.go:64] minikube
glog.Warningln_____
W0108 18:35:00.951179   17115 main.go:67] minikube
glog.Errorln_____
E0108 18:35:00.951190   17115 main.go:70] minikube
glog.V(0).Infoln_____
I0108 18:35:00.951201   17115 main.go:75] minikube
glog.V(1).Infoln_____
I0108 18:35:00.951212   17115 main.go:78] minikube
glog.V(2).Infoln_____
I0108 18:35:00.951222   17115 main.go:81] minikube
glog.V(3).Infoln_____
glog.V(4).Infoln_____

```