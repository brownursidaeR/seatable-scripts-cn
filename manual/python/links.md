# Links


#### Add link

添加链接，链接其他表记录

```python
base.add_link(link_id, table_name, other_table_name, row_id, other_row_id)
```

其中

* link_id: 链接列 data 属性下的 link_id (你可以获取 base 的 metadata，找到对应的列，然后找一下 data 字段下的 link_id 字段)
* table_name: 链接表的名字
* other_table_name: 被链接表的名字
* row_id: 链接行 id
* other_row_id: 被链接行的 id

##### 例子

```python
base.add_link('5WeC', 'real-img-files', 'contact', 'CGtoJB1oQM60RiKT-c5J-g', 'PALm2wPKTCy-jdJNv_UWaQ')
```

#### Update link

更新链接信息

```
update_link(self, link_id, table_id, other_table_id, row_id, other_rows_ids)
```

其中

* link_id: 链接列 data 属性下的 link_id 
* table_id: 链接表的 id
* other_table_id: 被链接表的 id
* row_id: 链接行 id
* other_rows_ids: 被链接行的 id 列表


##### 例子

```python
base.update_link(
        link_id='r4IJ',
        table_id='0000',
        other_table_id='kFoO',
        row_id='BXhEm9ucTNu3FjupIk7Xug',
        other_rows_ids=[
          'exkb56fAT66j8R0w6wD9Qg',
          'DjHjwmlRRB6WgU9uPnrWeA'
        ]
    )
```

#### Batch update links

批量更新链接信息

```
base.batch_update_links(link_id, table_id, other_table_id, row_id_list, other_rows_ids_map)
```

##### 例子

```python
link_id = "WaW5"
table_id ="0000"
other_table_id = "jtsf"
row_id_list = ["fRLglslWQYSGmkU7o6KyHw","eSQe9OpPQxih8A9zPXdMVA","FseN8ygVTzq1CHDqI4NjjQ"]
other_rows_ids_map = {
    	"FseN8ygVTzq1CHDqI4NjjQ":["OcCE8aX8T7a4dvJr-qNh3g","JckTyhN0TeS8yvH8D3EN7g"],
    	"eSQe9OpPQxih8A9zPXdMVA":["cWHbzQiTR8uHHzH_gVSKIg","X56gE7BrRF-i61YlE4oTcw"],
    	"fRLglslWQYSGmkU7o6KyHw":["MdfUQiWcTL--uMlrGtqqgw","E7Sh3FboSPmfBlDsrj_Fhg","UcZ7w9wDT-uVq4Ohtwgy9w"]
}

base.batch_update_links(link_id, table_id, other_table_id, row_id_list, other_rows_ids_map)
```

#### Remove link

移除某个链接

```python
base.remove_link(link_id, table_name, other_table_name, row_id, other_row_id)
```

##### 例子

```python
base.remove_link('5WeC', 'real-img-files', 'contact', 'CGtoJB1oQM60RiKT-c5J-g', 'PALm2wPKTCy-jdJNv_UWaQ')
```

#### Get link id

通过列名来获取链接的id

```python
base.get_column_link_id(table_name, column_name, view_name=None)
```

##### 例子

```python
base.get_column_link_id('Table1', '记录') # 返回链接的id，如‘aHL2’
```

