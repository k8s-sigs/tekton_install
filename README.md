# tekton_install
安装tekton-pipline
```
kubectl apply -f tekton_pipline.yaml
```
安装dashboard
```
kubectl apply -f tekton-dashboard.yaml

curl http://ip:9097
```

创建第一个task
```
kubectl apply -f task-hello.yaml
```
使用工具生成taskRun并运行
```
# use tkn's --dry-run option to save the TaskRun to a file
tkn task start hello --dry-run > taskRun-hello.yaml
# create the TaskRun
kubectl create -f taskRun-hello.yaml
```
查看日志
```
tkn taskrun logs --last -f
```