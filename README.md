import random
import time

diemcamxuc = [] #tạo list điêm cảm xúc
diem = 0 # 
diemcamxuc.append(diem)

def chaohoi():
    print("Hello bạn iu của chúng tôi ơi")
    print("Start")
    print("About our Web")

def intro():
    print("Xin chào bạn, Hôm nay bạn cảm thấy thế nào nè?")

def viewpoint():
    while True:
        print(sum(diemcamxuc))
        print("Ok")
        print("Reset")
        Okorreset=input("Exit or Reset:  ")
        if Okorreset=="exit":
          break
        if Okorreset=="reset":
          diemcamxuc.clear()
          return viewpoint()
      


def start():
    global diem
    print("1. Vui quá trùi vui")#vui
    print("2. Cũng bình thường thoi")#bth
    print("3. Đang buồn lắm òi")#buon
    opt = int(input("Cho tụi mình biết tâm trạng của bạn nha: "))
    while opt==1:
        time.sleep(1)
        #bắt đầu "vui":
        khen=("Thật tuyệt khi thấy bạn đang lan tỏa nguồn năng lượng tích cực","Bạn đang thể hiện một tinh thần rất đẹp đó","Sự tích cực của bạn không chỉ là cảm xúc, mà là giá trị thật sự khiến người khác được truyền cảm hứng")
        print(random.choice(khen))
        time.sleep(3)
        print("Tâm trạng của bạn phù hợp với các hoạt động:")
        time.sleep(1)
        hdvui=( "Đi bộ 1 vòng quanh nhà",
                "Tự thưởng cho bản thân 1 món đồ uống iu thích",
                "Chơi môn thể thao bạn thích",
                "Nghe 1 bài nhạc thật hay",
                "Viết ra 3 điều bạn muốn làm cho ngày mai")
        V1=random.choice(hdvui)
        print(V1)
        time.sleep(1)
        print("Chấp nhận nhiệm vụ")#11
        print("Roll nhiệm vụ khác")#22
        hoi=int(input("Bạn chọn phương án nào: "))
        #đồng ý tham gia:
        if (hoi==11):
            #tích điểm
            print("Điểm thưởng vui vẻ: +2")
            diem=2
            diemcamxuc.append(diem)
            quotevui=("Khi bạn vui, cả thế giới như rộng và sáng hơn", "Giữ chặt những khoảnh khắc hạnh phúc, nó là nhiên liệu cho những ngày sau","Niềm vui nhỏ cũng đáng được ăn mừng")
            print(random.choice(quotevui))
            print("Waiting...")
            while True:
              xacnhan=str(input("Đã làm xong nhiệm vụ "))
              if (xacnhan=="ok"):
                  print("thật xuất sắc")
                  nv2=str(input("bạn có muốn thêm 1 nhiệm vụ nữa không "))#yes/no
                  if (nv2=="yes"):
                      break
                  if (nv2=="no"):
                      return chaohoi()
              if (xacnhan=="no"):
                  print("Cố gắng hoàn thành nhé")
                  continue

        #không đồng ý
        if (hoi==22):
            print("loading...")
            time.sleep(2)
            continue


# ----------------- MAIN -----------------
while True:
  chaohoi()
  choice = input("start or intro or viewpoint: ")

  if choice == "intro":
      intro()
  if choice == "viewpoint":
      viewpoint()
  if choice == "start":
      start()
