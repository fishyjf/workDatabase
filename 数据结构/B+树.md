B+树是对B树的一种变形树，它与B树的差异在于：

- 有k个子结点的结点必然有k个关键码。
- **非叶结点仅具有索引作用，跟记录有关的信息均存放在叶结点中。**
- 树的所有叶结点构成一个有序链表，可以按照关键码排序的次序遍历全部记录。

**B树：有序数组+平衡多叉树；   
B+树：有序数组**链表+平衡多叉树

B+树的非叶子结点只包含导航信息，不包含实际的值，所有的叶子结点和相连的节点使用链表相连，便于区间查找和遍历。
B+ 树的优点在于：

IO次数更少：由于B+树在内部节点上不包含数据信息，因此在内存页中能够存放更多的key。 数据存放的更加紧密，具有更好的空间局部性。因此访问叶子节点上关联的数据也具有更好的缓存命中率。
遍历更加方便：B+树的叶子结点都是相链的，因此对整棵树的遍历只需要一次线性遍历叶子结点即可。而且由于数据顺序排列并且相连，所以便于区间查找和搜索。而B树则需要进行每一层的递归遍历。相邻的元素可能在内存中不相邻，所以缓存命中性没有B+树好。
