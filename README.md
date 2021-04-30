# Algorithm-Notes

- [進入演算法的世界](#進入演算法的世界)
- [常用的資料結構](#常用的資料結構)
- [排序 Sorting](#排序-sorting)
- [搜尋演算法](#搜尋演算法)
- [雜湊演算法](#雜湊演算法)
- [碰撞與溢位處理](#碰撞與溢位處理)
- [陣列演算法](#陣列演算法)
- [鏈結串列演算法](#鏈結串列演算法)
- [河內塔演算法](#河內塔演算法)
- [八皇后演算法](#八皇后演算法)
- [樹狀演算法](#樹狀演算法)
- [圖形演算法](#圖形演算法)
- [主元素問題](#主元素問題)
- [三個水桶問題](#三個水桶問題)
- [過河問題](#過河問題)
- [穩定匹配問題 Gale-Shapley 演算法](#穩定匹配問題-gale-shapley-演算法)
- [匈牙利演算法 Hungarian Algorithm](#匈牙利演算法-hungarian-algorithm)
- [蔡勒演算法 Zeller Algorithm](#蔡勒演算法-zeller-algorithm)
- [曲線擬合 Curve Fitting](#曲線擬合-curve-fitting)
- [非線性方程式求解](#非線性方程式求解)
- [幾何與電腦圖形學](#幾何與電腦圖形學)
- [傅立葉變換演算法 Fourier Transform](#傅立葉變換演算法-fourier-transform)
- [遺傳演算法 Genetic Algorithm](#遺傳演算法-genetic-algorithm)
- [尋徑演算法](#尋徑演算法)
- [賽局樹 Game Tree](#賽局樹-game-tree)
- [資料來源](#資料來源)

# 進入演算法的世界
## 定義
在有限步驟內解決數學問題的程式

## 四大特徵
- 確定性：每個步驟都是明確的，結果是可預期的
- 有窮性：必須是有限個步驟組成的過程，有確定的結束條件
- 可行性：最後能得出正確的結果
- 輸入和輸出：演算法是為了解決特定問題，問題來源是演算法的輸入，期望結果是演算法的輸出

## 條件
- 輸入(Input)：0個或多個輸入資料，必須有清楚的描述或定義
- 輸出(Output)：至少有一個輸出結果
- 明確性(Definiteness)：每個指令或步驟必須是簡潔明確且不含糊
- 有限性(Finiteness)：有限步驟後一定會結束
- 有效性(Effectiveness)：步驟清楚，能用紙筆計算求出答案


## 時間複雜度 O(f(n))
假如執行時間 <img src="https://github.com/ted10401/Algorithm-Notes/blob/main/Images/time_complexity_example.png"><br/>
則時間複雜度為 <img src="https://github.com/ted10401/Algorithm-Notes/blob/main/Images/time_complexity.png">


## 常見演算法
### 分治法 Divide and conquer Algorithm
將大問題分割成多個子問題，降低解決問題的複雜度<br/>
如快速排序法(Quick Sort)、遞迴演算法(Recursion)、大整數相乘法<br/>

基本思維
1. 分解：將問題分解為小問題<br/>
2. 解決：若小問題可解決則解決小問題，若不行則再次分解<br/>
3. 合併：將已解決的小問題透過某種規則合併起來<br/>

### 遞迴法 Recursion Algorithm
至少需有兩種條件<br/>
1. 可以反覆執行的遞迴過程<br/>
2. 跳出執行過程的出口<br/>

### 貪心法 Greed Algorithm
尋找最優解問題的常用方法，但無法保證解為最優解<br/>
每個步驟都用貪心原則，選取目前狀態下最好或最優的解<br/>
當局部最優解確定後，就不再進行回溯處理，只有在很少的情況下可以得到真正的最優解<br/>

基本思維<br/>
1. 建立最優解的模型<br/>
2. 將問題分解為一系列子問題，定義子問題的最優解<br/>
3. 取得子問題的局部最優解，將子問題堆疊出全域最優解<br/>

### 動態規劃法 Dynamic Programming Algorithm
解決多階段決策問題常用的最優化理論<br/>
將每個子問題的答案儲存起來供下次求解時直接取用<br>

### 疊代法 Iterative Algorithm

### 枚舉法、窮舉法
枚舉所有可能

### 回溯法 Backtracking Algorithm
枚舉法的一種，當條件不足時就回溯返回，嘗試其他解


# 常用的資料結構
## 陣列 Array
緊密相鄰的可數記憶體

## 鏈結串列 Linked List
相同資料型態的項目依照指定順序排列而成的線性串列

## Stack 堆疊
相同資料型態的組合，所有動作都在頂端進行，後進先出(Last In, First Out, LIFO)

## Queue 佇列
有序串列，先進先出(First In, First Out, FIFO)

## 樹狀結構
一個或一個以上節點(Node)組成<br/>
用於描述節點與節點之間『層次』的關係

### 分支度 Degree
該節點的子樹個數

### 階層或階度 Level
樹的層級

### 高度 Height
樹的最大階度

### 根 Root
沒有父節點的節點

### 樹葉、終端節點 Terminal Nodes
分支度為 0 的節點

### 父節點 Parent
上層節點

### 子節點 Children
下層節點

### 祖先 Ancestor、子孫 Descendent
祖先：樹根到該節點路徑上的節點<br/>
子孫：該節點子樹中的任一節點

### 兄弟節點 Siblings
有共同父節點的節點

### 非終端節點 Nonterminal Nodes
樹葉節點以外的節點

### 同代 Generation
相同階層數的節點

### 樹林 Forest
互斥樹的集合

### 二元樹 Binary Tree
最多能有兩個子節點<br/>
N 元樹的鏈結浪費率約為 (N - 1) / N<br/>
所以 N = 2 時鏈結浪費率最低<br/>


## 圖形簡介
討論兩個頂點之間『相連與否』的關係

### 尤拉環 Eulerian Cycle
當所有頂點的分支度皆為偶數，才能從某個頂點出發，經過每邊一次，回到起點

### 尤拉鏈 Eulerian Chain
當兩個頂點的分支度是奇數，其餘頂點分支度為偶數，才能從某個頂點出發，經過每邊一次，不一定回到起點

### 圖形的定義
G = (V, E)<br/>
V：所有頂點的集合<br/>
E：所有邊的集合<br/>

### 無向圖形 Graph
同邊的兩個頂點沒有次序關係<br/>
V = { A, B, C, D, E }<br/>
E = { (A, B), (A, E), (B, C), (B, D), (C, D), (C, E), (D, E) }<br/>
<img src="https://github.com/ted10401/Algorithm-Notes/blob/main/Images/graph.jpg">

### 有向圖形 Digraph
使用 <V1, V2> 表示方向性<br/>
V = { A, B, C, D, E }<br/>
E = { <A, B>, <B, C>, <C, D>, <C, E>, <E, D>, <D, B> }<br/>
<img src="https://github.com/ted10401/Algorithm-Notes/blob/main/Images/digraph.jpg">

## 雜湊表
儲存紀錄的連續記憶體

bucket 桶：儲存資料的位置，對應唯一的一個位址 bucket address<br/>
slot 槽：每筆紀錄可以包含複數欄位，slot 對應 bucket 中的欄位<br/>
collision 碰撞：兩筆不同資料經過雜湊計算後對應到相同位址<br/>
溢位：資料經過雜湊運算後對應的 bucket 已滿<br/>
synonym 同義字：經過雜湊運算後的數值相同<br/>
loading factor 載入密度：載入密度越大表示雜湊空間使用率越高，碰撞或溢位的機率越高<br/>
perfect hashing 完美雜湊：沒有碰撞也沒有溢位的雜湊函數<br/>

雜湊函數設計原則
1. 降低碰撞及溢位
2. 函數越容易計算越佳
3. 盡量將文字轉換成數字


# 排序 Sorting
將不規則的數值資料依照遞增或遞減方式重新排列<br/>
數值：比較數值大小<br/>
中文字串：比較中文內碼 (繁體 BIG5、簡體 GB)<br/>
非中文字串：比較 ASCII 碼<br/>

## 桶子排序法 Bucket Sort
假設未排序的資料在一範圍內分布，就將這些資料劃分為數個範圍，並逐一將未排序的資料放入範圍內並計數，最後根據計數將資料取出合併

時間複雜度：<img src="https://github.com/ted10401/Algorithm-Notes/blob/main/Images/complexity_n+k.png"><br/>
空間複雜度：<img src="https://github.com/ted10401/Algorithm-Notes/blob/main/Images/complexity_k.png"><br/>
n: 資料比數<br/>
k: 桶子數量<br/>
<img src="https://github.com/ted10401/Algorithm-Notes/blob/main/Images/bucket_sort.gif"><br/>

## 氣泡排序法 Bubble Sort
從第一個元素開始依序比較相鄰元素大小，如果順序有誤就對調元素
第一次掃描後能最後一個元素必定是最大或最小值

時間複雜度：<img src="https://github.com/ted10401/Algorithm-Notes/blob/main/Images/time_complexity_n2.png"><br/>
空間複雜度：<img src="https://github.com/ted10401/Algorithm-Notes/blob/main/Images/space_complexity_1.png"><br/>
<img src="https://github.com/ted10401/Algorithm-Notes/blob/main/Images/bubble_sort.gif"><br/>

## 選擇排序法 Selection Sort
在未排序數列中找到最大或最小的元素後，加入已排序數列中

時間複雜度：<img src="https://github.com/ted10401/Algorithm-Notes/blob/main/Images/time_complexity_n2.png"><br/>
空間複雜度：<img src="https://github.com/ted10401/Algorithm-Notes/blob/main/Images/space_complexity_1.png"><br/>
<img src="https://github.com/ted10401/Algorithm-Notes/blob/main/Images/selection_sort.gif"><br/>

## 插入排序法 Insert Sort
將未排列的資料逐一與已排列資料比較，並插入適當的位置

時間複雜度：<img src="https://github.com/ted10401/Algorithm-Notes/blob/main/Images/time_complexity_n2.png"><br/>
空間複雜度：<img src="https://github.com/ted10401/Algorithm-Notes/blob/main/Images/space_complexity_1.png"><br/>
<img src="https://github.com/ted10401/Algorithm-Notes/blob/main/Images/insert_sort.gif"><br/>


## 謝耳排序法 Shell Sort
可以減少插入排序法的資料搬移次數，將資料分成特定間隔的小區塊，用插入排序法排序個區塊內的資料，在逐漸減少間隔距離

時間複雜度：<img src="https://github.com/ted10401/Algorithm-Notes/blob/main/Images/time_complexity_n54.png"><br/>
空間複雜度：<img src="https://github.com/ted10401/Algorithm-Notes/blob/main/Images/space_complexity_1.png"><br/>
<img src="https://github.com/ted10401/Algorithm-Notes/blob/main/Images/shell_sort.gif"><br/>



## 合併排序法 Merge Sort
將一未排序數列分割成兩個未排序數列，持續分割直到數列元素小於一個，再逐一從已分割數列中取得最小、最大值合併成已排列數列，持續合併直到合併成一個數列。

1. 將長度為 N 的未排列數列分割成 2 個長度為 N/2 的數列
2. 將長度為 N/2 的未排列數列分割成 2 個長度為 N/4 的數列
3. 持續分割直到分割成 N 個長度為 1 的數列
4. 此時所有數列皆為已排序數列
5. 將 N 個長度為 1 的數列合併成 N/2 個長度為 2 的數列
6. 將 N/2 個長度為 2 的數列合併成 N/4 個長度為 4 的數列
7. 不斷合併直到合併成一組長度為 N 的數列

時間複雜度：<img src="https://github.com/ted10401/Algorithm-Notes/blob/main/Images/time_complexity_nlogn.png"><br/>
空間複雜度：<img src="https://github.com/ted10401/Algorithm-Notes/blob/main/Images/space_complexity_n.png"><br/>

## 快速排序法 Quick Sort
又稱為分割交換排序法，目前公認最佳的排序法，在資料中找到一個隨機設定的虛擬中間值，小於中間值的資料放左邊，大於中間值的資料放右邊，在同樣處理左右兩邊的資料，直到排序結束

時間複雜度：<img src="https://github.com/ted10401/Algorithm-Notes/blob/main/Images/time_complexity_nlogn.png"><br/>
空間複雜度：<img src="https://github.com/ted10401/Algorithm-Notes/blob/main/Images/space_complexity_logn.png"> ~ <img src="https://github.com/ted10401/Algorithm-Notes/blob/main/Images/space_complexity_n.png"><br/>
<img src="https://github.com/ted10401/Algorithm-Notes/blob/main/Images/quick_sort.gif"><br/>



## 基數排序法 Raix Sort
最無效鍵優先 Least Significant Digit First, LSD<br/>
從最右邊的位數開始比較<br/>
 
最有效鍵優先 Most Significant Digit First, MSD<br/>
從最左邊的位數開始比較<br/>

時間複雜度<br/>
Best Case：<img src="https://github.com/ted10401/Algorithm-Notes/blob/main/Images/time_complexity_d*n+r.png"><br/>
Worst Case：<img src="https://github.com/ted10401/Algorithm-Notes/blob/main/Images/time_complexity_d*n+r.png"><br/>
Average Case：<img src="https://github.com/ted10401/Algorithm-Notes/blob/main/Images/time_complexity_d*n+r.png"><br/>

d = 執行回合數<br/>
n = 數列長度<br/>
r = 基數<br/>

空間複雜度<br/>
<img src="https://github.com/ted10401/Algorithm-Notes/blob/main/Images/space_complexity_n*r.png"><br/>

<img src="https://github.com/ted10401/Algorithm-Notes/blob/main/Images/raix_sort.gif"><br/>




# 搜尋演算法
搜尋分為靜態搜尋、動態搜尋，根據搜尋過程中被搜尋的表格或資料是否異動來分類<br/>
靜態搜尋：指資料在搜尋過程中，該搜尋資料不會有增加、刪除、或更新等行為<br/>
動態搜尋：指資料在搜尋過程中，會經常性地增加、刪除或更新<br/>

## 循序搜尋、線性搜尋 Sequential Search
逐次搜尋每筆資料，優點為在搜尋前不需要做任何的處理與排序，缺點為搜尋速度較慢，<br/>
最好的情況搜尋1次就找到資料，最差的情況是搜尋 N 筆資料後未找到資料<br/>

## 二分搜尋法 Binary Search
資料須事先排序才可以使用二分搜尋法進行搜尋<br/>
主要是將資料分成兩等分，比較搜尋值與中間值的大小，如果搜尋值小於中間值，則可以確定搜尋值在資料的前半段，依序分割資料直到找到鍵值<br/>

## 內插搜尋法 Interpolation Search
二分搜尋法的改良版本，利用內插公式預測資料的所在位置，再利用二分法逐步逼近


# 雜湊演算法
## 除法 Division Hash
將資料除以某個常數，取餘數作為索引

## 中間平方法 Mid-Square
將資料乘以自己，在取中間的某段數字

## 折疊法 Folding
1. 將資料轉換成一串數字
2. 將數字拆成數個部分
3. 將數字相加

## 邊界折疊法 Folding at the Boundaries
1. 將資料轉換成一串數字
2. 將數字拆成數個部分
3. 將偶數位段或奇數位段反轉
4. 將數字相加

## 數位分析法
適用於資料不會修改，且為數字型態的資料，將重複性高的部分刪除，擷取適當的數字

# 碰撞與溢位處理
雜湊法的理想情況是所有資料經過雜湊函數運算後都能得到不同的值<br/>
當雜湊函數運算後得到相同的位址則發生碰撞<br/>
當 Bucket 滿了則發生溢位<br/>

## 線性探測法
當碰撞發生時，以線性方式往後找尋空儲存空間

## 平方探測法
線性探測的一個缺點是類似的鍵值常常會聚集在一起，因此可以考慮使用平方探測法加以改善<br/>
當碰撞發生時，下個搜尋位址是 (f(x) + ((B - 1) / 2)^2) mod B 與 (f(x) - ((B - 1) / 2)^2) mod B<br/>
B 必須是 4j + 3 的質數

## 再雜湊法
發生碰撞時，以設置好的一系列雜湊函數依序運算鍵值，直到找到空儲存空間


# 陣列演算法

# 鏈結串列演算法
可分為靜態資料結構 Static Data Structure、動態資料結構 Dynamic Data Structure

## 靜態資料結構
將有序串列的資料使用連續記憶體空間來儲存，在編譯時就配置給相關的變數<br/>
優點是設計時相當簡單及讀取與修改資料的時間固定<br/>
缺點是新增或刪除資料時，需要移動大量的資料<br/>

## 動態資料結構
鏈結串列 Linked List 又稱為動態資料結構，使用不連續記憶空間來儲存<br/>
優點是資料的新增或刪除相當方便<br/>
缺點是設計資料結構時較為麻煩，且搜尋資料時，需要透過循序搜尋找到該資料為止<br/>

## 矩陣
### 矩陣相加
兩矩陣列數與行數必須相等

### 矩陣相乘
若 A 矩陣為 m * n 矩陣<br/>
則 B 矩陣須為 n * p 矩陣<br/>
才可滿足矩陣相乘條件<br/>

### 轉置矩陣
將 A 矩陣的行座標元素與列座標元素相互調換，即為 A 的轉置矩陣 A’

## 單向鏈結串列
單向鏈結串列需要定義一個指標欄位


## 河內塔演算法
規則
1. 直徑小的套環永遠在直徑大的套環上<br/>
2. 套環可任意移動<br/>
3. 每次只能移動一個套環<br/>
<img src="https://github.com/ted10401/Algorithm-Notes/blob/main/Images/tower_of_hanoi.gif"><br/>

## 八皇后演算法
規則
1. 皇后可以直吃、橫吃及斜吃<br/>
2. 後放入的新皇后需要考慮是否會被已放入的舊皇后吃掉<br/>
<img src="https://github.com/ted10401/Algorithm-Notes/blob/main/Images/8_queen.png"><br/>


# 樹狀演算法
樹與圖最大的差異是，樹是不包含迴路的連通無向圖

完滿二元樹 Full Binary Tree
<img src="https://github.com/ted10401/Algorithm-Notes/blob/main/Images/tree_full_binary_tree.jpg"><br/>

完整二元樹 Complete Binary Tree
<img src="https://github.com/ted10401/Algorithm-Notes/blob/main/Images/tree_complete_binary_tree.jpg"><br/>

歪斜樹 Skewed Binary Tree
<img src="https://github.com/ted10401/Algorithm-Notes/blob/main/Images/tree_skewed_binary_tree.jpg"><br/>

嚴正二元樹 Strictly Binary Tree
<img src="https://github.com/ted10401/Algorithm-Notes/blob/main/Images/tree_strictly_binary_tree.jpg"><br/>

## 二元樹走訪
<img src="https://github.com/ted10401/Algorithm-Notes/blob/main/Images/tree_binary_tree_traversal.jpg"><br/>

中序走訪 Inorder Traversal：左子樹 > 樹根 > 右子樹<br/>
FDGHIBEAC<br/>

後序走訪 Postorder Traversal：左子樹 > 右子樹 > 樹根<br/>
FHIGDEBCA<br/>

前序走訪 Preorder Traversal：樹根 > 左子樹 > 右子樹<br/>
ABDFGHIEC<br/>

## 二元樹節點搜尋
比節點小就往左子樹搜尋，比節點大就往右子樹搜尋，直到找到節點

## 二元樹節點插入
節點插入後仍要保持二元搜尋樹的特性<br/>
若樹中有該筆資料，不進行插入<br/>
若樹中沒有該資料，則加入該資料<br/>

## 二元樹節點刪除
刪除的節點是樹葉：將其父節點指向 None<br/>
刪除的節點有一個子樹：將其父節點指向子樹<br/>
刪除的節點有兩個子樹：將預刪除節點的左子樹最大者向上提，或是將預刪除節點的右子樹最小者向上提<br/>

## 堆積樹排序法 Heap Tree
最大堆積樹
1. 是一個完整二元樹
2. 父節點大於或等於子節點
3. 樹根是最大值

最小堆積樹
1. 是一個完整二元樹
2. 父節點小於或等於子節點
3. 樹根是最小值


# 圖形演算法
## 先深後廣走訪法 Depth First Search, DFS
走訪節點時，將與該節點相鄰的節點放入堆疊 Stack 中

## 先廣後深走訪法 Breadth First Search, BFS
走訪節點時，將與該節點相鄰的節點放入佇列 Queue 中

## 最小花費擴張樹 Minimum Spanning Tree, MST
### Prim 演算法
1. 從 V 集合中取任一頂點放入 U 集合
2. 從 V 集合中取得與 U 集合頂點形成最小花費的頂點，且不能造成迴路
3. 反覆執行步驟 2 直到 U 集合等於 V 集合
### Kruskal 演算法
1. 將成本由小到大排列
2. 選擇成本最低的邊線且不能形成迴路
3. 反覆執行步驟 2 直到邊線遍歷完畢

## 圖形最短路徑法 Shortest Path
### Dijkstra 演算法
1. 從 V 集合中選擇一頂點並加入 S 集合
2. 找出該頂點到各頂點的距離
3. 選擇最小距離頂點並加入 S 集合
4. 重複執行步驟 2 直到 S 集合 = V 集合

時間複雜度：<img src="https://github.com/ted10401/Algorithm-Notes/blob/main/Images/complexity_M+NlogN.png"><br/>
空間複雜度：<img src="https://github.com/ted10401/Algorithm-Notes/blob/main/Images/complexity_M.png"><br/>

### A* 演算法
A* 演算法與 Dijkstra 演算法最大的差異是 A* 演算法除了起點到各頂點的實際權重之外，也會預估各頂點到終點的預測權重，可以有效的減少不必要的搜尋動作

#### 距離評估函數
曼哈頓距離 Manhattan Distance<br/>
<img src="https://github.com/ted10401/Algorithm-Notes/blob/main/Images/astar_manhattan_distance.png"><br/>

切比雪夫距離 Chebysev Distance<br/>
<img src="https://github.com/ted10401/Algorithm-Notes/blob/main/Images/astar_chebysev_distance.png"><br/>

歐氏幾何平面直線距離 Euclidean Distance<br/>
<img src="https://github.com/ted10401/Algorithm-Notes/blob/main/Images/astar_euclidean_distance.png"><br/>

### Floyd 演算法
Dijkstra 演算法只能求出某一頂點到其他頂點的最短距離<br/>
如果要求出圖形任意兩頂點的最短距離就必須要使用 Floyd 演算法<br/>
假設頂點數量為 N，則需要執行 N 次迴圈逐一產生 A^1 ~ A^n 個矩陣<br/>

時間複雜度：<img src="https://github.com/ted10401/Algorithm-Notes/blob/main/Images/complexity_N3.png"><br/>
空間複雜度：<img src="https://github.com/ted10401/Algorithm-Notes/blob/main/Images/complexity_N2.png"><br/>

### Bellman-Ford 演算法
Dijkstra 演算法雖然好，但不能解決負權邊的圖<br/>
Bellman-Ford 演算法是無論是在思維上、還是程式碼實作上都堪稱完美的最短路徑演算法<br/>

核心程式碼
```csharp
for(int k = 1; k <= n - 1; k++)  
{  
    for(int i = 1; i <= m; i++)  
    {  
        if(dis[v[i]] > dis[u[i]] + w[i])  
        {  
            dis[v[i]] = dis[u[i]] + w[i];  
        }  
    }  
}  
```
n: 頂點個數<br/>
m: 邊個數<br/>
dis: 紀錄頂點到其餘各頂點的最短路徑<br/>

時間複雜度：<img src="https://github.com/ted10401/Algorithm-Notes/blob/main/Images/complexity_NM.png"><br/>
空間複雜度：<img src="https://github.com/ted10401/Algorithm-Notes/blob/main/Images/complexity_M.png"><br/>

### 佇列優化的 Bellman-Ford 演算法
Bellman-Ford 演算法會鬆弛所有的頂點與邊，即使該頂點已求得最短路徑，佇列優化的 Bellmain-Ford 則是在此基礎上，只針對最短路徑發生變化的點的相鄰邊執行鬆弛操作

時間複雜度：<img src="https://github.com/ted10401/Algorithm-Notes/blob/main/Images/complexity_NM.png"><br/>
空間複雜度：<img src="https://github.com/ted10401/Algorithm-Notes/blob/main/Images/complexity_M.png"><br/>

# 主元素問題
問題：已知一總數為 N 的序列 ，其中有一個數字出現的次數大於 N/2，請找出這個數字<br/>
舉例：3、3、1、1、3、2、3 數列中，出現次數超過 50% 的數是 3<br/>

## 暴力法
分別計數各數字的出現次數，出現次數最多的數即為主元素

## 排序法
1. 排序後紀錄各數字的出現次數，當某數字出現次數大於前一個數字的出現次數及更新數字
2. 其中由於某個數字必定大於 N/2，所以可以直接找到 N/2 位置的數，此數字即為主元素

## 桶子排序法
1. 將每個數字分別放入桶子內紀錄次數
2. 若數字跨度很大，則將數字離散處理

## 快速排序法
1. 隨機選擇一數字做為劃分點，小於此數字移動到劃分點左邊，大於此數字移動到右邊
2. 如果劃分點右邊的數字較多則往右邊找新的劃分點，反之往左邊找新的劃分點
3. 如果新的劃分點等於原劃分點，則該數字即為主元素

## 抵銷法
當碰到兩數不相同的情況時，刪除兩數，最後剩下的數即為主元素


# 三個水桶問題
有三個容積分別為 3公升、5公升、8公升的水桶，其中 8公升的水桶裝滿水，要如何將 8公升的水等分成兩份。

1. 定義起始狀態 (8, 0, 0)
2. 定義結束狀態 (4, 4, 0)
3. 定義合法動作 <br/>
A水桶有水，且B水桶未倒滿<br/>
倒完水的狀態沒有出現過<br/>

4. 執行合法動作<br/>
5a. 若執行合法動作後，狀態是結束狀態則結束搜尋<br/>
5b. 若執行合法動作後，狀態不是結束狀態則回到步驟 4<br/>


# 過河問題
河的左岸有三個妖怪、三個和尚，每次最多兩個人過河，最少一個人過河，當妖怪數大於和尚數會吃掉和尚，要如何讓三個妖怪與三個和尚都到達河的右岸。

1. 定義起始狀態 (3, 3, 0, 0, Left)
2. 定義結束狀態 (0, 0, 3, 3, Right)
3. 定義合法動作<br/>
當和尚數大於零時，妖怪數不能大於和尚數<br/>
至少需要有一個人過河<br/>

4. 執行合法動作<br/>
5a. 若執行合法動作後，狀態是結束狀態則結束搜尋<br/>
5b, 若執行合法動作後，狀態不是結束狀態則回到步驟 4<br/>


# 穩定匹配問題 Gale-Shapley 演算法
虛擬碼<br/>
初始化<img src="https://github.com/ted10401/Algorithm-Notes/blob/main/Images/gale_shapley_1.png">、<img src="https://github.com/ted10401/Algorithm-Notes/blob/main/Images/gale_shapley_2.png">，所有的 m 和 w 都是未匹配狀態
```csharp
while(存在 m 是未匹配狀態，且尚未對每個 w 都匹配過)  
{  
    選擇一個 m;  
    w = m 優先度較高且尚未匹配的對象;  
    if(w 是未匹配狀態)  
    {  
        將 m、w 設定為匹配狀態  
    }  
    else  
    {  
        m’ = w 目前匹配的對象;  
        if(m’ 的優先度比 m 優先度高)  
        {  
            m 保持未匹配狀態;  
        }  
        else  
        {  
            將 m、w 設定為匹配狀態  
            將 m’ 設定為未匹配狀態  
        }  
    }  
}  
```

# 匈牙利演算法 Hungarian Algorithm
是一種二分匹配演算法

基本流程
```csharp
將圖 G 最大匹配初始化為空  
while(從 Xi 點開始在圖 G 中找到新的增廣路徑)  
{  
    將增廣路徑假如到最大匹配中;  
}  
輸出圖 G 的最大匹配;  
```

尋找增廣路徑 Augment Path 是匈牙利演算法的核心<br/>
二分圖中的增廣路徑具有以下性質<br/>
1. 路徑中邊的條數是奇數
2. 路徑的起點在二分圖的左半邊，終點在二分圖的右半邊
3. 路徑上的點一個在左半邊，一個在右半邊，交替出現，整條路徑上沒有重複的點
4. 只有路徑的起點和終點都是未覆蓋的點，路徑上其他的點都已經配對
5. 對路徑上的邊按照順序編號，所有奇數編號的邊都不再已知的匹配中，所有偶數編號的邊都在已知的匹配中
6. 對增廣路徑進行『取反』操作，新的匹配數就比已知匹配數增加一個，也就是說，可以得到一個最大匹配

搜尋增廣路徑的流程
```csharp
while(從 Xi 的鄰接串列中找到下一個關鍵頂點 Yj)  
{  
    if(頂點 Yj 不再增廣路徑上)  
    {  
        將 Yj 加入增廣路徑;  
        if(Yj 是未覆蓋點或者從與 Yj 相關連的的頂點 (Xk) 能找到增廣路徑)  
        {  
            將 Yj 的關聯頂點修改為 Xi;  
            從頂點 Xi 開始有增廣路徑，返回 true;  
        }  
    }  
    從頂點 Xi 開始沒有增廣路徑，返回 false;  
}  
```

# Kuhn-Munkres 演算法
求最大權或最小權匹配的演算法


# 蔡勒演算法 Zeller Algorithm
<img src="https://github.com/ted10401/Algorithm-Notes/blob/main/Images/zeller_algorithm.png"><br/>
c: 世紀數 - 1，如 21 世紀，則 c = 20<br/>
m: 月數，m 需大於等於 3，小於等於 14，1 月和 2 月看做上一年的 13 月和 14 月<br/>
y: 年份，取西元年後兩位，如 1998 年，y = 98，2001 年，y = 1<br/>
d: 某月內的日數<br/>

## 判斷是否為閨年
```csharp
private bool IsLeapLear(int year)  
{  
    return ((year % 4 == 0) && (year % 100 != 0)) || year % 400 == 0;  
}  
```

## 取得該月天數
```csharp
private int[] m_daysOfMonth = { 31, 28, 31, 30, 31, 30, 31, 31, 30, 31, 30, 31 };  
private int GetDaysOfMonth(int year, int month)  
{  
    if(month < 1 || month > 12)  
    {  
        return 0;  
    }  
  
    int days = m_daysOfMonth[month - 1];  
    if(month == 2 && IsLeapLear(year))  
    {  
        days++;  
    }  
  
    return days;  
}  
```

## 取得該日星期
```csharp
private int ZellerWeek(int year, int month, int day)  
{  
    int m = month;  
    int d = day;  
  
    if(month <= 2)  
    {  
        m += 12;  
        year--;  
    }  
  
    int y = year % 100;  
    int c = year / 100;  
  
    int w = (y + y / 4 + c / 4 - 2 * c + (13 * (m + 1) / 5) + d - 1) % 7;  
    if(w < 0)  
    {  
        w += 7;  
    }  
  
    return w;  
}  
```


# 曲線擬合 Curve Fitting
定義是指用連續曲線近似刻劃或比擬平面上一組離散點所表示的座標之間的函數關係，是一種用解析運算式逼近離散資料的方法。

## 最小平方法 Least Squares
假設擬合多項式 <img src="https://github.com/ted10401/Algorithm-Notes/blob/main/Images/least_squares_1.png"><br/>
離散的各點到這條曲線的平方合則為<br/>
<img src="https://github.com/ted10401/Algorithm-Notes/blob/main/Images/least_squares_2.png"><br/>

## 高斯消去法
可用來求解多元一次線性方程式、矩陣的秩、可逆方陣的矩陣


# 非線性方程式求解
## 公式法 
<img src="https://github.com/ted10401/Algorithm-Notes/blob/main/Images/nonlinear_equation_1.png"><br/>
<img src="https://github.com/ted10401/Algorithm-Notes/blob/main/Images/nonlinear_equation_2.png"><br/>
<img src="https://github.com/ted10401/Algorithm-Notes/blob/main/Images/nonlinear_equation_3.png"><br/>
<br/>
<img src="https://github.com/ted10401/Algorithm-Notes/blob/main/Images/nonlinear_equation_4.png">，有兩個不相等實數解<br/>
<img src="https://github.com/ted10401/Algorithm-Notes/blob/main/Images/nonlinear_equation_5.png">，有兩個相等實數解<br/>
<img src="https://github.com/ted10401/Algorithm-Notes/blob/main/Images/nonlinear_equation_6.png">，沒有實數解，有兩個不相等複數解<br/>

## 二分逼近法
f(x) 如果存在實數 k，使 f(k) = 0，x = k 則為函數 f(x) 的零點。<br/>
如果 f(x) 是[單調函數](https://zh.wikipedia.org/wiki/%E5%8D%95%E8%B0%83%E5%87%BD%E6%95%B0)，且 f(a) 和 f(b) 異號，代表 [a, b] 之間一定有零點，此時就可以使用二分逼近法近似地找到這個零點。<br/>

(1) 如果 <img src="https://github.com/ted10401/Algorithm-Notes/blob/main/Images/bisection_method_1.png">，則 <img src="https://github.com/ted10401/Algorithm-Notes/blob/main/Images/bisection_method_2.png"> 就是零點<br/>
(2) 如果 <img src="https://github.com/ted10401/Algorithm-Notes/blob/main/Images/bisection_method_3.png">，則零點在區間 <img src="https://github.com/ted10401/Algorithm-Notes/blob/main/Images/bisection_method_4.png">，令 <img src="https://github.com/ted10401/Algorithm-Notes/blob/main/Images/bisection_method_5.png">，回到 (1)<br/>
(3) 如果 <img src="https://github.com/ted10401/Algorithm-Notes/blob/main/Images/bisection_method_6.png">，則零點在區間 <img src="https://github.com/ted10401/Algorithm-Notes/blob/main/Images/bisection_method_7.png">，令 <img src="https://github.com/ted10401/Algorithm-Notes/blob/main/Images/bisection_method_5.png">，回到 (1)<br/>

## 牛頓法 Newton’s Method
<img src="https://github.com/ted10401/Algorithm-Notes/blob/main/Images/newtons_method.png">


# 幾何與電腦圖形學
## 向量
有大小又有方向的量<br/>
<img src="https://github.com/ted10401/Algorithm-Notes/blob/main/Images/vector_1.png"><br/>
<img src="https://github.com/ted10401/Algorithm-Notes/blob/main/Images/vector_2.png"><br/>
<img src="https://github.com/ted10401/Algorithm-Notes/blob/main/Images/vector_3.png"><br/>

## 向量加、減法
<img src="https://github.com/ted10401/Algorithm-Notes/blob/main/Images/vector_plus_minus_1.png">、<img src="https://github.com/ted10401/Algorithm-Notes/blob/main/Images/vector_plus_minus_2.png"><br/>
<img src="https://github.com/ted10401/Algorithm-Notes/blob/main/Images/vector_plus_minus_3.png"><br/>
<img src="https://github.com/ted10401/Algorithm-Notes/blob/main/Images/vector_plus_minus_4.png"><br/>

滿足以下性質：<br/>
<img src="https://github.com/ted10401/Algorithm-Notes/blob/main/Images/vector_plus_minus_5.png"><br/>
<img src="https://github.com/ted10401/Algorithm-Notes/blob/main/Images/vector_plus_minus_6.png"><br/>

## 向量內積、點積 Dot Product
<img src="https://github.com/ted10401/Algorithm-Notes/blob/main/Images/vector_dot_1.png"><br/>
<img src="https://github.com/ted10401/Algorithm-Notes/blob/main/Images/vector_dot_2.png">，<img src="https://github.com/ted10401/Algorithm-Notes/blob/main/Images/vector_dot_3.png">表示向量 P 和 Q 的夾角

幾何意義<br/>
取絕對值即為垂直投影的長度<br/>

如果 <img src="https://github.com/ted10401/Algorithm-Notes/blob/main/Images/vector_dot_3.png">，則 P 和 Q 之間的夾角大於 90 度<br/>
如果 <img src="https://github.com/ted10401/Algorithm-Notes/blob/main/Images/vector_dot_4.png">，則 P 和 Q 之間的夾角小於 90 度<br/>
如果 <img src="https://github.com/ted10401/Algorithm-Notes/blob/main/Images/vector_dot_5.png">，則 P 和 Q 之間的夾角等於 90 度<br/>

```csharp
private float Dot(Vector2 point1, Vector2 point2)  
{  
    return point1.x * point2.x + point1.y * point2.y;  
}  
```

## 向量外積、叉積 Cross Product
<img src="https://github.com/ted10401/Algorithm-Notes/blob/main/Images/vector_cross_1.png"><br/>

幾何意義<br/>
座標原點(0, 0)、P、Q、P + Q 所組成的平行四邊形面積<br/>

滿足以下性質：<br/>
<img src="https://github.com/ted10401/Algorithm-Notes/blob/main/Images/vector_cross_2.png"><br/>

<img src="https://github.com/ted10401/Algorithm-Notes/blob/main/Images/vector_cross_3.png"> 是 P 和 Q 所在平面的法向量<br/>
如果 <img src="https://github.com/ted10401/Algorithm-Notes/blob/main/Images/vector_cross_4.png">，則 Q 在 P 的逆時針方向<br/>
如果 <img src="https://github.com/ted10401/Algorithm-Notes/blob/main/Images/vector_cross_5.png">，則 Q 在 P 的順時針方向<br/>
如果 <img src="https://github.com/ted10401/Algorithm-Notes/blob/main/Images/vector_cross_6.png">，則 Q 與 P 共線 (方向可能相反)<br/>

```csharp
private float Cross(Vector2 point1, Vector2 point2)  
{  
    return point1.x * point2.y - point2.x * point1.y;  
}  
```

## 內積、外積與長度的關係
<img src="https://github.com/ted10401/Algorithm-Notes/blob/main/Images/vector_length_relation.png"><br/>
```csharp
private void BaseHeight(Vector2 p, Vector2 p1, Vector2 p2)  
{  
    Vector2 v1 = p1 - p;  
    Vector2 v2 = p2 - p;  
  
    float base = Mathf.Abs(Dot(v1, v2)) / VectorLength(v1);  
    float height = Mathf.Abs(Cross(v1, v2)) / VectorLength(v1);  
}  
```

## 內積、外積與角度的關係
<img src="https://github.com/ted10401/Algorithm-Notes/blob/main/Images/vector_angle_relation.png"><br/>
```csharp
private void SinCosTheda(Vector2 p, Vector2 p1, Vector2 p2)  
{  
    Vector2 v1 = p1 - p;  
    Vector2 v2 = p2 - p;  
  
    float l1 = VectorLength(v1);  
    float l2 = VectorLength(v2);  
  
    float cos = Dot(v1, v2) / l1 / l2;  
    float sin = Cross(v1, v2) / l1 / l2;  
  
    float theda = Mathf.Acos(cos);  //[0, π]
    float theda = Mathf.Asin(sin);  //[-π/2, π/2]
}  
```

## 內積與向量夾角的關係
<img src="https://github.com/ted10401/Algorithm-Notes/blob/main/Images/vector_dot_angle_relation.png"><br/>

## 外積與向量旋轉的關係
<img src="https://github.com/ted10401/Algorithm-Notes/blob/main/Images/vector_cross_rotate_relation.png"><br/>

## 點與點的關係
```csharp
private float PointDistance(Vector2 point1, Vector2 point2)  
{  
    return VectorLength(point2 - point1);  
}  
  
private float VectorLength(Vector2 vector2)  
{  
    return Mathf.Sqrt(vector2.x * vector2.x + vector2.y * vector2.y);  
}  
```

## 點與線的關係 
```csharp
private float Distance_PointLine(Vector2 point, Vector2 linePoint1, Vector2 linePoint2)  
{  
    Vector2 v1 = point - linePoint1;  
    Vector2 line = linePoint2 - linePoint1;  
    return Mathf.Abs(Cross(v1, line)) / VectorLength(line);  
}  
  
private bool IsPointInLine(Vector2 linePoint1, Vector2 linePoint2, Vector2 point)  
{  
    return PointDistance(linePoint1, linePoint2) == (PointDistance(linePoint1, point) + PointDistance(linePoint2, point));  
}  
```

## 點與矩形的關係
```csharp
private bool IsPointInRect(Rect rect, Vector2 point)  
{  
    float x = (point.x - rect.xMin) * (point.x - rect.xMax);  
    float y = (point.y - rect.yMin) * (point.y - rect.yMax);  
    return x <= 0 && y <= 0;  
}  
```

## 點與圓的關係
```csharp
private bool IsPointInCircle(Vector2 center, float radius, Vector2 point)  
{  
    return PointDistance(center, point) <= radius;  
}  
```

## 直線
<img src="https://github.com/ted10401/Algorithm-Notes/blob/main/Images/line.png"><br/>

## 圓
<img src="https://github.com/ted10401/Algorithm-Notes/blob/main/Images/circle_1.png"><br/>
<img src="https://github.com/ted10401/Algorithm-Notes/blob/main/Images/circle_2.png">：圓心座標<br/>
<img src="https://github.com/ted10401/Algorithm-Notes/blob/main/Images/circle_3.png">：半徑<br/>

## 橢圓
<img src="https://github.com/ted10401/Algorithm-Notes/blob/main/Images/oval_1.png"><br/>
<img src="https://github.com/ted10401/Algorithm-Notes/blob/main/Images/oval_2.png">：圓心座標<br/>
<img src="https://github.com/ted10401/Algorithm-Notes/blob/main/Images/oval_3.png">：長軸<br/>
<img src="https://github.com/ted10401/Algorithm-Notes/blob/main/Images/oval_4.png">：短軸<br/>

# 傅立葉變換演算法 Fourier Transform
時域訊號，座標軸是時間軸，表示訊號強度隨時間變化的情況。<br/>
頻域訊號，座標軸是頻率，表示訊號在各個頻率上的相對功率強度。<br/>

許多情況下，訊號的某些特徵在時域表現不明顯，但如果轉換到頻域，這些特徵就一目了然。

## 離散傅立葉轉換 Discrete Fourier Transform, DFT
什麼是傅立葉變換？<br/>
任何連續週期訊號可以由一組適當的正弦曲線組合而成，所以滿足一定條件的連續函數都可以表示成一系列三角函數或者它們的積分的線性組合形式，這個轉換就是傅立葉變換。

## 快速傅立葉變換 Fast Fourier Transform, FFT
基本思維就是利用週期性和對稱性，將 N 個點的 DFT 分解成 n 個 N/n 點的 DFT，從而減少運算量。<br/>
週期性：<img src="https://github.com/ted10401/Algorithm-Notes/blob/main/Images/fft_1.png"><br/>
對稱性：<img src="https://github.com/ted10401/Algorithm-Notes/blob/main/Images/fft_2.png"><br/>

實務上有需要建議使用 Real FFT<br/>
[Real FFT Algorithms](http://www.robinscheibler.org/2013/02/13/real-fft.html)

# 遺傳演算法 Genetic Algorithm
達爾文『物競天擇，適者生存』，借鑑這種生物體自然選擇和自然遺傳機制的隨機搜尋演算法，透過評估函數進行優勝劣汰的選擇，透過交配和變異模擬生物的進化。

基因 Gene：單獨的遺傳因數，包含一組不能在拆分的生物學特徵<br/>
染色體 Chromosome：一組基因的組合<br/>
種群 Population：生物的進化以群體的形式進行<br/>
個體 Individuals<br/>
交配 Crossover：繁殖的過程，將種群中的個體兩兩進行部分基因編碼片段的互換<br/>
基因突變 Mutation：直接替換個體基因中的某個或某幾個編碼<br/>
選擇 Selection：按造一定的規則從上一代種群中選擇個體遺傳到下一代<br/>
適應度 Fitness：個體對環境的適應程度，適應度低的個體會逐步淘汰<br/>

# 尋徑演算法
<img src="https://github.com/ted10401/Algorithm-Notes/blob/main/Images/path_finding.png"><br/>

# 賽局樹 Game Tree
賽局可以理解為有限參與者進行有限策略選擇的競爭性活動，如下棋、打牌、競技、戰爭等。

## 零和賽局 Zero-sum Game
零和代表有輸有贏，不存在雙贏

## 全資訊
參與賽局的雙方進行決策時能夠了解的資訊是公開和透明的

## 極大極小值演算法 Minimax
總是選擇最小化對手的最大利益

極大值節點，先手的選擇節點，會**選擇對先手最有利的評估最大值**<br/>
極小值節點，後手的選擇節點，會**選擇對先手最不利的評估最小值**，因為這一手是站在後手的立場進行選擇

```csharp
private int MiniMax(node, depth, isMaxPlayer)  
{  
    if(depth == 0)  
    {  
        return Evaluate(node);  
    }  
  
    int score = isMaxPlayer ? -INFINITY : INFINITY;  
    foreach(node's child nodes)
    {  
        int value = MiniMax(child_node, depth - 1, !isMaxPlayer);  
        if(isMaxPlayer)  
        {  
            score = max(score, value);  
        }  
        else  
        {  
            score = min(score, value);  
        }  
    }  
}  
```

## 負極大值演算法 Negamax
由於極大極小值演算法需要個別區分目前的節點是最大值還是最小值節點，而消除了極大極小值的演算法即為負極大值演算法。

核心基礎<br/>
<img src="https://github.com/ted10401/Algorithm-Notes/blob/main/Images/negamax.png"><br/>

```csharp
private int NegaMax(node, depth, color)  
{  
    if(depth == 0)  
    {  
        return color * Evaluate(node);  
    }  
 
    int score = -INFINITY;  
    foreach(node's child nodes)  
    {  
        int value = -NegaMax(child_node, depth - 1, -color);  
        score = max(score, value);  
    }  
}  
```

## 剪枝演算法 Alpha-beta Pruning
<img src="https://github.com/ted10401/Algorithm-Notes/blob/main/Images/alpha.png"> 剪枝：極小值節點搜尋極大值時，極大值中的最小值為 <img src="https://github.com/ted10401/Algorithm-Notes/blob/main/Images/alpha.png">，若另一極小值節點的極大值比  還小，則可終止節點搜尋<br/>
<br/>
<img src="https://github.com/ted10401/Algorithm-Notes/blob/main/Images/beta.png"> 剪枝：極大值節點搜尋極小值時，極小值中的最大值為 <img src="https://github.com/ted10401/Algorithm-Notes/blob/main/Images/beta.png">，若另一極大值節點的極小值比  還大，則可終止節點搜尋<br/>
<br/>
搜尋開始時，設定<br/>
<img src="https://github.com/ted10401/Algorithm-Notes/blob/main/Images/alpha_infinity.png"><br/>
<img src="https://github.com/ted10401/Algorithm-Notes/blob/main/Images/beta_infinity.png"><br/>
在搜尋過程中，逐步收窄這個範圍，即為 <img src="https://github.com/ted10401/Algorithm-Notes/blob/main/Images/alpha_beta.png"> 剪枝

### 井字遊戲
估值函數：(先手雙連子數 - 後手雙連子數) x 10 + (先手空行數 - 先手空行數) - 後手雙連子數<br/>
空行數：行、列、斜線上只有己方棋子或空個子<br/>
雙連子數：行、列、斜線上有兩個己方棋子，且沒有對方棋子<br/>
```csharp
public int Evaluate(GameState gameState, PlayerType maxPlayerType)  
{  
    int max1 = gameState.GetNoCount(maxPlayerType);  
    int max2 = gameState.GetConnectCount(maxPlayerType);  
    int max3 = gameState.GetThreeCount(maxPlayerType);  
  
    PlayerType minPlayerID = GetPeerPlayer(maxPlayerType);  
    int min1 = gameState.GetNoCount(minPlayerID);  
    int min2 = gameState.GetConnectCount(minPlayerID);  
    int min3 = gameState.GetThreeCount(minPlayerID);  
  
    if (max3 > 0)  
    {  
        return 9999;  
    }  
      
    if(min3 > 0)  
    {  
        return -9999;  
    }  
  
    return (max2 - min2) * 10 + (max1 - min1) - min2;  
}
```
<img src="https://github.com/ted10401/Algorithm-Notes/blob/main/Images/ooxx.gif"><br/>

# 參考來源
[圖說演算法：使用Python](https://www.books.com.tw/products/0010779462)
[演算法的樂趣：23個程式設計必學主題與應用實例](https://www.books.com.tw/products/0010691123)
[Vector](http://web.ntnu.edu.tw/~algo/Point.html)
