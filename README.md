# sistem-rental-mobil-lite

#search
def linear_search(suzuki, cari):
    
    index = len(suzuki)
    value = False
    suzuki1 = []
    
    for i in range(0, index):
        if cari == suzuki[i]:
            value = True
            suzuki1.append(i)
    
    if value == True:
        print("data ketemu")
        for i in suzuki1:
            print("di index : ", i)
    
    else:
        print("data tidak ada")
        print("ulangi program")
        exit()
        
suzuki = ["XL7", "ERTIGA", "JUMMY", "APV_ARENA", "GRAND_VITANA"]
print("HALLO SELAMAT DATANG DI FAMILY CAR")
print("macam-macam tipe mobil : ", suzuki)

cari = (input("tipe mobil apa yang kamu inginkan :"))
linear_search(suzuki, cari)

#stack

stack = [suzuki]
print("data sekarang : ", stack)

stack.append(cari)
print("data masuk :", cari)
print("data sekarang :", stack)

out=stack.pop()
print("data keluar :", out)
print("data sekarang :", cari)

confirm_answer = input(f"apakah ini benar mobil pilihan anda ? {cari} [yes/no]: ")
if confirm_answer == "no":
    print("program akan di ulangi jika ingin menganti mobil")
    exit()
elif confirm_answer == "yes":
    if (cari):
        print(f"{cari}adalag mobil yang anda pilih, berikut adalah nominal nya")

#buble sort
def bubbles_sort(biaya):
    n = len(biaya)
    for i in range(n):
        for j in range(0, n-i-1):
            if biaya[j] > biaya[j+1]:
                biaya[j], biaya[j+1] = biaya[j+1], biaya[j]

if __name__== "__main__":
    biaya = [645, 344, 290, 195, 290, 1175, 900]
    print("biaya sebelum di urutkan:")
    print(biaya)
    bubbles_sort(biaya)
    print("biaya setelah di urutkan:")
    print(biaya)
    print("nominal harga yang lebih besar maka akan menambah durasi sewa")

#graph
graph = {
    "Mobil A":["Mobil B", "Mobil C"],
    "Mobil B":["Mobil A", "Mobil C"],
    "Mobil C":["Mobil A", "Mobil B", "Mobil D"],
    "Mobil D":["Mobil C", "Mobil E"],
    "Mobil E":["Mobil D"]
}
def graph_coloring(graph):
    colors={}
    availabe_colors=["pagi","siang","malam","sore"]
    for node in graph:
        neighbor_colosr= {colors[neighbor]for neighbor in graph[node]if neighbor in colors}
        for color in neighbor_colosr:
            color[node] = color
            break
        
    return colors

schedule = graph_coloring(graph)
print("hasil penjadwalan dan alokasi mobil:")
for mobil, waktu in schedule.items():
    print(f"{mobil}: {waktu}")

pilihan = (input("kapan anda ingin mengambil mobil :"))

confirm_answer =()
if confirm_answer == (graph):
    print("terimakasih atas kerja sama, nanti saya hubungi lagi")
    exit()
else:
    print("hari tidak sesuai mohon ulangi")
    exit()
