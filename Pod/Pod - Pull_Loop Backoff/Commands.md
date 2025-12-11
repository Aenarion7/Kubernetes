# Prerequisite:

CLuster is created
You are creating the pod, but something went wrong and the pod keeps restarting and failing.
Also works if for example container is getting error and is in restarting loop.

# Description
Error: ImagePullBackOff - pojawia się gdy kublet nie może zrobić Image Pull
Pull będzie sięwydażał w regularnym interwale czasowym dlatego należy przerwać.

# Delete pods:
    kubectl delete -f 01-simple-pod.yaml