人口密度:
import requests
import pandas as pd

url = "https://www.ris.gov.tw/rs-opendata/api/v1/datastore/ODRP048/106"
res = requests.get(url)
filename = "F:\\population_density.json"
with open(filename,'wb') as f:
    f.write(res.content)
    
密度讀取:
import requests, json
import pandas as pd

新北市 = 0
臺北市 = 0
基隆市 = 0
桃園市 = 0
新竹市 = 0
苗栗縣 = 0
臺中市 = 0
彰化縣 = 0
南投縣 = 0
雲林縣 = 0
嘉義縣 = 0
臺南市 = 0
高雄市 = 0
屏東縣 = 0
宜蘭縣 = 0
花蓮縣 = 0
臺東縣 = 0
新竹縣 = 0
嘉義市 = 0
澎湖縣 = 0

filename = f"F:\\population_density.json"
with open(filename, 'r', encoding='utf-8') as f:
    datas = json.loads(f.read())

for i in range(370):
    if datas["responseData"][i]["site_id"][0:3]=="新北市":
        新北市 = 新北市 + int(datas["responseData"][i]["people_total"])
    elif datas["responseData"][i]["site_id"][0:3]=="臺北市":
        臺北市 = 臺北市 + int(datas["responseData"][i]["people_total"])
    elif datas["responseData"][i]["site_id"][0:3]=="基隆市":
        基隆市 = 基隆市 + int(datas["responseData"][i]["people_total"])
    elif datas["responseData"][i]["site_id"][0:3]=="桃園市":
        桃園市 = 桃園市 + int(datas["responseData"][i]["people_total"])
    elif datas["responseData"][i]["site_id"][0:3]=="新竹市":
        新竹市 = 新竹市 + int(datas["responseData"][i]["people_total"])
    elif datas["responseData"][i]["site_id"][0:3]=="苗栗縣":
        苗栗縣 = 苗栗縣 + int(datas["responseData"][i]["people_total"])
    elif datas["responseData"][i]["site_id"][0:3]=="臺中市":
        臺中市 = 臺中市 + int(datas["responseData"][i]["people_total"])
    elif datas["responseData"][i]["site_id"][0:3]=="彰化縣":
        彰化縣 = 彰化縣 + int(datas["responseData"][i]["people_total"])
    elif datas["responseData"][i]["site_id"][0:3]=="南投縣":
        南投縣 = 南投縣 + int(datas["responseData"][i]["people_total"])
    elif datas["responseData"][i]["site_id"][0:3]=="雲林縣":
        雲林縣 = 雲林縣 + int(datas["responseData"][i]["people_total"])
    elif datas["responseData"][i]["site_id"][0:3]=="嘉義縣":
        嘉義縣 = 嘉義縣 + int(datas["responseData"][i]["people_total"])
    elif datas["responseData"][i]["site_id"][0:3]=="臺南市":
        臺南市 = 臺南市 + int(datas["responseData"][i]["people_total"])
    elif datas["responseData"][i]["site_id"][0:3]=="高雄市":
        高雄市 = 高雄市 + int(datas["responseData"][i]["people_total"])
    elif datas["responseData"][i]["site_id"][0:3]=="屏東縣":
        屏東縣 = 屏東縣 + int(datas["responseData"][i]["people_total"])
    elif datas["responseData"][i]["site_id"][0:3]=="宜蘭縣":
        宜蘭縣 = 宜蘭縣 + int(datas["responseData"][i]["people_total"])
    elif datas["responseData"][i]["site_id"][0:3]=="花蓮縣":
        花蓮縣 = 花蓮縣 + int(datas["responseData"][i]["people_total"])
    elif datas["responseData"][i]["site_id"][0:3]=="臺東縣":
        臺東縣 = 臺東縣 + int(datas["responseData"][i]["people_total"])
    elif datas["responseData"][i]["site_id"][0:3]=="新竹縣":
        新竹縣 = 新竹縣 + int(datas["responseData"][i]["people_total"])
    elif datas["responseData"][i]["site_id"][0:3]=="嘉義市":
        嘉義市 = 嘉義市 + int(datas["responseData"][i]["people_total"])
    elif datas["responseData"][i]["site_id"][0:3]=="澎湖縣":
        澎湖縣 = 澎湖縣 + int(datas["responseData"][i]["people_total"])
    
print(新北市,臺北市,基隆市,桃園市,新竹市,苗栗縣,臺中市,彰化縣,南投縣,雲林縣,嘉義縣,臺南市,高雄市,屏東縣,宜蘭縣,花蓮縣,臺東縣,新竹縣,嘉義市,澎湖縣)
