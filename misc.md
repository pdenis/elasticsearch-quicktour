Misc
====

Monitoring : ​
     * GET /_status​
     * GET /_cluster/health​
​
Backup : ​
     * PUT /_snapshot/my_backup​

```json
{​
	"type": "fs",  # AWS / Azure are availables​
	"settings": {​
		"location": "/mount/backups/my_backup",​
		"compress": true​
 	}​
}​
```