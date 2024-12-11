การสอบของ DSToolBox

จริงๆต้องสร้างgit
ลบ git
Clone git
สร้างเจค+สภาพแวดล้อม
เปิดใช้สภาพแวดล้อม
ติดตั้ง django
สร้างdjango startapp myapp
สร้างเจค A-E ตามที่ได้
อัพขึ้น branch function…
สร้าง docker
รัน docker

1.สร้าง repository ใหม่ "รหัสประจำตัว-ฟังก์ชัน" พร้อม .gitignore
-> เข้าไปที่ github.com แล้วทำการสร้าง repository กด New กรอกชื่อ folder “toolbox_65114540420”
-สร้าง mkdir “name folder” ก่อนแล้วทำการ git clone https://github.com/pisit65/65114540420
 จากนั้น cd เข้าที่ 65114540420

2.สร้าง web project
->สร้างโปรเจค   django-admin startproject web_project หรือ 
	    python -m django startproject web
->สร้างสภาพแวดล้อมให้เว็บ python -m venv venv 
แล้วทำการเปิดใช้งาน venv\Scripts\activate
ทำการติดตั้ง django pip install django
เริ่มโปรเจค django-admin startproject web_project


3.commit push
-ทำการล็อคอิน github
          gh auth login 
-การเลือกเพิ่มทั้งหมดของ project ที่เราสร้างเข้าไปใน github
git add .
-การเอาขึ้น github แล้วคอมเม้นไว้ว่าเอาขึ้นเพื่ออะไร เช่น -m "Initial Django project setup"
git commit -m "commit first"
-การเพิ่มไฟล์ที่จะเอาขึ้นไปยัง branch main
git push origin main

4.ลบ directory แล้ว clone ใหม่
-การลบโฟลเดอร์ทั้งหมด
	rmdir /s /q toolbox_65114540420
-สร้าง mkdir “name folder” ก่อนแล้วทำการ git clone https://github.com/pisit65/65114540420
 จากนั้น cd เข้าที่ 65114540420
->สร้างสภาพแวดล้อมให้เว็บ python -m venv venv 
แล้วทำการเปิดใช้งาน venv\Scripts\activate
ทำการติดตั้ง django pip install django
เริ่มโปรเจค django-admin startproject web_project
		python -m django startproject web

gitignore สามารถเพิ่มเข้าไปได้เลยตอนสร้าง repo
5.สร้างและแก้ไข branch ตามชื่อฟังก์ชันs
-เช็ค branch
	git branch

-สร้าง branch ใหม่
git branch branch_name

-การสลับไปใช้ branch อื่นนอกจาก main
git checkout -b   ชื่อ branch       หรือ
git checkout   ชื่อ branch

-การ push ไปยัง branch ที่สร้างเสร็จ
	git push -u origin functionsA

6.เพิ่มฟังก์ชันบนเว็บตามที่กำหนด
เพิ่ม A-E ในไฟล์ view และ model

7.commit push
-การเลือกเพิ่มทั้งหมดของ project ที่เราสร้าง
เข้าไปใน github
git add .
-การเอาขึ้น github แล้วคอมเม้นไว้ว่าเอาขึ้นเพื่ออะไร เช่น -m "Initial Django project setup"
git commit -m "commit sec"
-การเพิ่มไฟล์ที่จะเอาขึ้นไปยัง branch main
git push origin main



8.สร้าง docker image
ใช้ docker images เพื่อเช็คไฟล์ที่มีอยู่
->docker images
สร้าง dockerfile ไฟล์
	echo > dockerfile

FROM python:3.12


WORKDIR /myproject


COPY . .


RUN pip install django


RUN python manage.py migrate


EXPOSE 9999


CMD ["python", "manage.py", "runserver", "0.0.0.0:9999"]
-แล้วต่อด้วยคำสั่งเพื่อสร้าง docker
docker build -t myproject .





9.เปิดเว็บด้วย docker
-คำสั่งรันไฟล์ 
docker run -p 9999:9999 myproject

-คำสั่งเปิดเว็บ
http://localhost:9999/

