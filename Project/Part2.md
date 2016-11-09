###Part 2: Queries on the data in mongodb.

#
1.	db.yelp.business.find({$or: [{"full_address" : {$regex : ".*89117.*"}},{"full_address" : {$regex : ".*89122.*"}}]}).count()


2.	db.yelp.business.find({ "city" : "Las Vegas"}).count()

3.	 db.yelp.business.find({ "loc" : { $geoWithin : { $centerSphere: [ [ -80.839186, 35.226504 ], 5 / 3963.2 ] } } }).count()

4.	db.yelp.review.find({"_id" : ObjectId("581a51abbd45e57b60ae9203")}).count()

5.	db.yelp.review.find({ $and : [{"_id" : ObjectId("P1fJb2WQ1mXoiudj8UE44w")}, {"stars" : 5}]}).count()

6.	db.yelp.user.find({ "yelping_since" : {$lte:"2011-11"}}).count()

7.  INCOMP	db.yelp.user.find({"name":"Lynda"}, {_id:1})

8.	db.yelp.user.aggregate([{$group:{_id:"review_count",averageReviewCount:{$avg:"$review_count"}}}])

9.	db.yelp.user.find({"elite":{"$ne":[]}},{"_id":0,"user_id":1,"name":1,"elite":1})

10.	db.yelp.user.find({"elite":{"$ne":[]}}).sort({"elite":-1}).limit(1)
