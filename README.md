# Proyecto

# Pipeline data process

![pipeline](assets/data.png)

### About Data Base:

### Query to filter Tutelas

```json

db.judgemnts.aggregate( [
   {$count: "myCount"},
   {$match: { "file_id": /^T/i }}
])


db.judgemnts.aggregate( [
   {$match: { "file_id": /^T/i }}
])

db.judgemnts.count({ "file_id": /^T/i })

db.judgemnts.find({ "file_id": /^T/i })


db.judgemnts.aggregate( [
   {
        $group: {
            "file_id": /^T/i,
             count: { $sum: 1 }
        }
   }
])


db.judgemnts.aggregate( [
   {
        $group: {
           _id: "$file_id",
           judgemnts: { $push: "$date" }
        }
   }
])


db.judgemnts.aggregate( [

   {
         $match: { "file_id": /^T/i }
   },
   {
        $group: {
           _id: "$file_id",
           count: { $sum: 1 }
        }
   }
])

```


### Shape DataFrame
* Initial: (4410, 12)
* Result: (1862, 9)

### General Dataset statistics

* Number of variables	9
* Number of observations	1862
* Missing cells	0
* Missing cells (%)	0.0%
* Duplicate rows	0
* Duplicate rows (%)	0.0%
* Total size in memory	131.0 KiB
* Average record size in memory	72.1 B

## ===================

#### Variable types

* Categorical	3
* Numeric	6
