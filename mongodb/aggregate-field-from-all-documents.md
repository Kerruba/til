# Aggregate field from all documents in a collection

I've found myself in the need of sum all the values in a field of different documents.
You can achieve such result with the `$group` operator, providing a null id

```
db.<collection>.aggregate([
	{
		$group: {
			_id: null,
			<fieldname>: {
				$sum: <expression>
			}
		}
	}
}
])
```
[source](https://docs.mongodb.com/manual/reference/operator/aggregation/group/)