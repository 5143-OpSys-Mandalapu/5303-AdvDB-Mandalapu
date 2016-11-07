###Part 2: Queries on the data in mongodb.

#
1.	db.yelp.business.find({$or: [{"full_address" : {$regex : ".*75205.*"}},{"full_address" : {$regex : ".*75225.*"}}]})


2.	db.yelp.business.find({ "city" : "Bethel Park"})

3.	 db.yelp.business.find({ "loc" : { $geoWithin : { $centerSphere: [ [ -98.5329437, 33.8719656 ], 5 / 3963.2 ] } } })

4.	db.yelp.review.find({"_id" : ObjectId("581a51abbd45e57b60ae9203")})

5.	db.yelp.review.find({ $and : [{"_id" : ObjectId("581a51abbd45e57b60ae9203")}, {"stars" : 5}]})

6.	db.yelp.user.find({ "yelping_since" : {$lte:"2011-11"}})

7.  INCOMP	db.yelp.user.find({"name":"Lynda"}, {_id:1})

8.	db.yelp.user.aggregate([{$group:{_id:"review_count",averageReviewCount:{$avg:"$review_count"}}}])

9.	db.yelp.user.find({"elite":{"$ne":[]}},{"_id":0,"user_id":1,"name":1,"elite":1})

10.	
