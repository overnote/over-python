## 一 Py连接MySql示例
```py
import pymysql

def main():

    # 1. 链接数据库
    conn = pymysql.connect(host='localhost',port=3306,database='mydb',user='root',password='123456',charset='utf8')

    # 2. 获取游标对象
    cursor =  conn.cursor()

    # 3. 组织字符串
    # sql = """select * from goods where name="%s";""" % find_item_name
    # print(sql)
    sql = """select * from goods where name="apple";"""

    # 4. 执行查询语句
    cursor.execute(sql, [find_item_name])

    # 5. 显示相应的结果
    print(cursor.fetchall())

    # 6. 关闭
    cursor.close()
    conn.close()

if __name__ == "__main__":
    main()
```

## 二 Python连接Redis示例
```py
import redis

#使用ｄｅｃｏｄｅ＿ｒｅｓｐｏｎｓｅ指定为ｔｒｕｅ,得到字符串类型
redis_store = redis.StrictRedis(host='127.0.0.1',port=6379,decode_responses=True)

redis_store.set('name','zs')

name = redis_store.get('name')
```

## 三 Python连接MongoDB示例
```py

```