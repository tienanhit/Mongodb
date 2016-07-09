# Mongodb
Guide building project with mongodb
#1. Setup
	link guide: https://docs.mongodb.com/manual/tutorial/install-mongodb-on-linux/
	Command sudo apt-get update. sudo apt-get install -y mongodb-org
	Centos:
		https://docs.mongodb.com/manual/tutorial/install-mongodb-on-red-hat/
		update: sudo yum update
		setting vim: sudo yum install -y vim
		create a file repo: vim /etc/yum.repos.d/mongodb-org-3.2.repo
		write file:
			[mongodb-org-3.2]
			name=MongoDB Repository
			baseurl=https://repo.mongodb.org/yum/redhat/$releasever/mongodb-org/3.2/x86_64/
			gpgcheck=1
			enabled=1
			gpgkey=https://www.mongodb.org/static/pgp/server-3.2.asc
		
			save and close: esc :wq
			
		setting db lastest: sudo yum install -y mongodb-org
# 2. Command mongodb start
	ubuntu:
		start: sudo service mongodb start
		stop db: sudo service mongodb stop
		reset db: sudo service mongodb restart
	centos:
		start: sudo service mongod start
		stop: sudo service mongod stop
		reset: sudo service mongod reset
	
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
	 
