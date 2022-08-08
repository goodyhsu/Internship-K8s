# MongoDB & Mongo Express
Note: https://hackmd.io/0GINzuC4Qa-56OIjkk3-lA#MongoExpress-Config

## Overview
* 4 files
    * `mongo-secret.yaml`: required mongodb secret
    * `mongo.yaml`: mongodb deployment
    * `mongo-configmap.yaml`:  ConfigMap, `mongo-express` connects to `mongodb`
    * `mongo-express.yaml`: mongo express deployment