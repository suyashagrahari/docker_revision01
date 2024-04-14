FROM node:latest 

# first line bta rha h ki hmara base file kya hona chhaiye 

WORKDIR /myapp
# second line hme ye bta rha h ki hmara jo khali conatiner h image m , us conatiner m hme knha apne program ko run krana h 
# iske liye hmne ek working directory bnaya conatiner m jiska name myapp h 

# Copy package.json and package-lock.json to the working directory
COPY package.json .
COPY package-lock.json .


COPY . . 
# third line hme ye bta rha h ki hmara jo program h use copy kr do conatiner main. -> isme phela dot hamre program ko bta rha h jnha hm currnetly hain and second dot container ke main directory ko represent kr rha h mtlb myapp ko ise hm /myapp krke bhi represent kr skte hain 
# ab ye basicallu hmare program ko container ke main directory myapp main copy kr dega 

RUN npm install
# fourth line ye bta rha ki jb image bnega aur uska hm jb conatiner bnayengye to ye cmd run kr jayega--- q ki hmne node moduke isme nhi daal rkha h ab hme apne react project ko chlane ke liye node module to chiye isliye conatiner bnne se phele ye chl jayega jisse ye create ho jayega conatiner m 

# ye chro steps hamre image ko bnane ke liye use hota h iske baad hm conatiner m apne program ko run kaise krengye uske liye hme 5th line likhna padega 

# RUN npm start bhi krk skte hain but ye turant chl jayega - turant na chale aur jb type kre tbhi chale to uske liye hm cmd main ise dete hain 

# chuki ye 3000 port pr chl rha h to hm ise expose kr dengye ki ye 3000 port no pr chale -- aur ye optional hota h kro ya na kro 
 
EXPOSE 3000 


CMD [ "npm","run","dev" ]
# 5th line hmare program ko chlane ke liye use kiya jata h --> jb hm cmd pr npm start likhenge tbhi ye chalega 

# ye sara process to hogya hmara container create krne ke liye 
# ab docker image bnane ke liye hm -----     *********(docker build .)***********     run krte h cmd pr --- . represent krta h ki hmara docker file knha h --- dot m hm apne docker file ka location dete hain mtlb uska directory --- ab save krke docker build . run krengye jisse hmara image create ho jayega 


# hm chaiye to apne image ko name bhi de skte hain using ******** (dcoker build -t myapp:01 .) *************


# ab hm apne image ko dekhne ke liye ***** (docker image ls) krengye jisse hm dekh sakengye hmara image bna ya nhi - aur ye hme image id bnakr de dedega 

# ab image bnne ke baad hm apne conatiner ko run krne ke liye hm ----      ********( docker run imageid)**********     dete hain jisee hmara conatiner run ho jata h aur create ho jata h hmare computer or laptop main but hm iske andr create hue program ko apne laptop pr nhi chla skte q ki ye abhi container ke andr run kr rha h hamra program --- aur hm container ko apne laptop ke through aise acccess nhi kr skte hain 

# ab hm docker coantiner kaunn kaun se chl rhe hain usko hm --- ************ (docker ps) **************** ke help se dekh skte hain isko run krne ke baad jo jo container hmare laptop pr currently chl rhe hongye wo ajyengye aur uske details ajynegye 

# ab is container ko bnd krne ke liye hm ***********(docker stop container_name ) ***************** run kr dengye jisse hmara conatiner stop ho jayega 

# ab hm apne conatine main chl rhe program ko agr apne laptop pr chlana chhate hain to hm port binding krengye use ***********( docker run -p 3000 : 3000 container_id) *************  phela port ye btata h ki hm kaun se port pr ise apne laptop ya machone pr chalana chhate hain and dusra container ka expose port bta rha h ki kaun se port pr container m program run kr rha h 

# TERMINAL KO FREE KRNE KE LIYE :-  hm ***** -d  ******** (detach mode) ko use krengye use hm -p (port binding se phele use krengye isse hmara terminal free ho jayega) ab isme hm apna koi bhi comnad run kr skte hain;

# RUNING MULTIPLE CONATINERS :-  isme hm sbhi conatiner ka port binding alg alg kr dete hain to utna hmara conatiner run ho jayega aur conatiner ko ek specific name allocate ho jata h ise hm chnage bhi kr skte hain 


# RUNNING CONATAINER DEKHNE KE LIYE : - (docker ps )

# SBHI CONATINER KO DEKHNE KE LIYE : - (docker ps -a)
# sabhi images ko dekhne ke liye :- (docker images)

# DOCKER KO REMOVE KRNE KE LIYE :- (docker rm conatiner_id) ka use krte hain

#  docker m container ko baar baar stop aur remove se bchane ke liye hm (docker run -d --rm -p 3000:3000 container_id or image_id)
# isme jb hum container ko stop krte hain to cinatiner apne aap remove ho jayega 


# CONTAINER KA NAME DENE KE LIYE : - (docker run -d --rm --name "mynewapp" -p 3000:3000 image_nameot id)

# IMAGE KO DLETE KRNE KE LIYE HM ::- docker rmi myhnewapp:0

# ab is image ko rgister krne ke liye phele hm docker hub pr account bnate hai then ukse baad wnha create ropsoitory krte h then fir hm terminal m ************ (docker login) ************** cmd chlate hain 


# BASICALLY HME JB KOI IMAGE DOCKER PR PUSH KRNA HOTA H TO HM PHELE USKI REPOSITORY BNATE H MTLB IMAGE NAME FIR US IMAGE M HM APNA IMAGE INCERT KRNE KE LIYE USE LOCALLY IMAGE BNAKE USME BUILD KRNA PADEGA JISKE KARN US NAME SE HMARA IAMGE BN JAYEGA AB HM DOCKER PUSH KRENGYE TO WO IMAGE USI REOPSITORY PR JAYEGA 

# docker push suyashagrahari2121/docker_practice:tagname
# chuki ise image name pr hm push krna chhate hain aur ye image name locally hmare dokcer m present nhi h to hm is name ka image create krengye phle 



# ********* (docker build -t suyashagrahari2121/docker_practice:01 . )************** ye cmd chlayengye image bnane ke liye 

# fir ab hm is image ko push kr dengye ************ (docker push suyashagrahari2121/docker_practice:01) **************
# ab hmara docker image create ho jayega docker hubpr 


# AB AGR HME IMAGES KE NAME KO YA TAGS KO CHNAGE KRNA HO TO :- **********(docker tag image_name1:01 image_name2:02) ************


# AB HME JNHA APNA PROJECT USE KRNA H WNHA HM ISE PULL KR LENG



# *********************** DOCKER VOLUME ***************************************
# (docker voulme ls)
# basically voulme ko hm ******** (-v myvolume:/myapp/)**************** ke dwarra create krte hain , volume conatiner ke bahar bnta h ise docker manage krta h aur ye hmesha rheta h chiaye hmara conatiner delete hi q na ho jaye 


# DOCKER VOLUME - BIND METHOD - ************** (-v local path of server.txt{ye container ke bahar ka file h} : /myapp/server.txt/ {ye container ke andr ka file h }) AB HM IN DONO ko bind kr dengye jisse hm koi bhi changes bahar wale file  m krengye to wo container ke andr bhi changesg hongye 

# *************** (.dockerignore) ***************************
# isme hm jo file dalengye wo docker m images create hone ke time ignore ho jayega 


# WORKING WITH API 
# 1):-  isme hm container ke andr se container ke bahar ke api ko call krengye 
# ab isme hm jb kisi api ko bahar se call krte hain to hm kuch chize import krte h jaise axios hua jo ki node m hota h aur requests hua jo ki python m hua ab inko bhi hme apne docker file m include krna padega to ab isme liye hm DOCKER FILE M ************ (RUN pip intall requests) *********** ya agr hm nodejs m hain to hm ************* (RUN npm install axios) ************  krengye 


# 2) :- AB HM APNE CONATINER KE ANDR PYTHON PROGRAM YA NODEJS PROGRAM SE CONTAINER KE BAHAR DATA BASE KO ACCESS KRNA CHAHTE HAIN JISKE LIYE HME JNHA HMARA HOST -> ******** (localhost)******* h use change krke ************(host.docker.internal) ************** krna padega 

# 3):-  AB HM KAYI SARE CONATINER KO AAPS M LINK KRENGYE 
# for example hmare pass ek container h jisme ek m node js chl rha h aur dusre container m mongodb -> ab inko ek dusre se linke krne ke liye hm jb mongodb container ko run krte hain ya build krte hain to hm kuch ENVIROMENT VARIABLE(-env) SET KRTE HAIN -> like root-password , database name then usek baad hm aone nodejs ke program m root-password m aur database name m whi value dengye aur is baar host m hm mongodb container la ip address (docker isnpect conatiner_id) daal dengye now ab hmara program ready h mtlb hmare dono container ek dusre se linke hogye h  ----- > isme ek problem ye hain ki jb hmara mogodb ka containerrun krega uske baad hi hm nodejs wala container run kr skengye 

# ab is problem ko hm network ke through solve kr skte hain --> hm kya krengye basically hm ek network create krengye then uske baad hm cintainer ko us network m incert kr dengye jisse unke bich connection easily bn jayega 



# ***************************** NETWROK **************************
# network ka command dekhne ke liye hm (docker network --help) chhlayengye

# NETWORK BNNA EKE LIYE HM ***************** (DOCKER NETWORK CRETAE NETWORK_NAME) ********************

# ab hm jis conatiner ko imse rkhna chhate hain use assign krngye -> docker run -it(interactive termianl) --rm(remove) -d(detach) -v(creating voulume) --name conatiner_name  -p(port binding) 3000(host):3000(container host) --network my-net(network name jisme is container ko insert krna h) image_id (container_id)

# isko run krne ke baad an hme jis contianer ko is conatiner ke sath jodna h uske *****(host)***** m kewal docker coantiner ka name de dengye 

# ******************************* DOCKER COMPOSE *********************************

# DOCKER COMPAOSE ke help se hm multiple conatiner ko handle kr skte h ya jod skte hain ek dusre se ---> aur ye is liye aya q ki hme phele bhut badi command likhni padti thi --> like command m hme -it , -p , -d , -v , binding , --network , --env variable sb declare ya dena pdta tha jo ki bhut jada complex ho jata h 

