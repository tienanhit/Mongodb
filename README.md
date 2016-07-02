# Mongodb
Guide building project with mongodb
#1. Setup
	link guide: https://docs.mongodb.com/manual/tutorial/install-mongodb-on-linux/
	Command sudo apt-get update. sudo apt-get install -y mongodb-org
# 2. Command mongodb start
	start: sudo service mongodb start
	stop db: sudo service mongodb stop
	reset db: sudo service mongodb restart
	use db: mongo
# 3. User DB
	- show all db
			show dbs
	- select a db or Create db
			use mydb
	- Drop a DB
			use mydb
			db.dropDatabase()
# 4. Collection DB (Same collum in sql)
	- create collection db 
			db.createCollection(name,options)
		Ex: db.createCollection("mydb",{ capped : true, autoIndexID : true, size : 6142800, max : 10000 })
			You can see: http://www.tutorialspoint.com/mongodb/mongodb_create_collection.htm
	- drop collection db
		db.COLLECTION_NAME.drop()
#	5. Interactive document
		- Insert document
			db.COLLECTION_NAME.insert(document)
			ex:	db.mydb.insert({"name":"Tien Anh","age":"24"})
			ex2: db.mydb.insert({"name":"Tien Anh","age":"24"},{"city":"Ha Noi","coutry":"Viet Nam"})
		- Query DB
			All 
				db.COLLECTION_NAME.find()
			Results in a formatted
				db.COLLECTION_NAME.find().pretty()
			Where
				db.COLLECTION_NAME.find("WHERE").pretty()
				ex: db.mydb.find({"name":"Tien Anh"})
			See more: http://www.tutorialspoint.com/mongodb/mongodb_query_document.htm
	
