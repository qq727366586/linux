PUT /megacorp/_doc/1
{
"first_name": "John",
"last_name": "Smith",
"age": 25,
"about": " i love go rock",
"interests": ["sport", "music"]
}

PUT /megacorp/_doc/2
{
"first_name": "John2",
"last_name": "Smith2",
"age": 25,
"about": " i love go rock2",
"interests": ["sport", "music2"]
}

PUT /megacorp/_doc/3
{
"first_name": "John3",
"last_name": "Smith3",
"age": 25,
"about": " i love go rock3",
"interests": ["sport", "music3"]
}

#获取某个索引
GET /megacorp/_doc/1

#获取某个索引下的所有
GET /megacorp/_search

#

