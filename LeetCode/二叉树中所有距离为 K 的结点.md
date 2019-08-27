#### 二叉树中所有距离为 K 的结点

[题目](https://leetcode-cn.com/problems/all-nodes-distance-k-in-binary-tree/)

```
#include<iostream>
#include<vector>
using namespace std;
typedef struct node {
	int data;
	struct node *lchild, *rchild;
}tree;
//创建二叉树
tree *creat()
{
	int c;
	tree *t;
	scanf("%d", &c);
	if (c == -1)
		t = NULL;
	else
	{
		t = (tree*)malloc(sizeof(tree));
		t->data = c;
		t->lchild = creat();
		t->rchild = creat();
	}
	return t;
}
class Method {
public:
	vector<int> array;
	vector<int> distancek(tree* root, tree* target, int k) {
		//不存在
		if (root == NULL || target == NULL) {
			return {};
		}
		//所求结点为根结点
		if (k == 0) {
			return { target->data };
		}
		//遍历二叉树
		dfs(root, target, k);
		return array;
	}

	int dfs(tree* root, tree* target, int k) {
		if (root == NULL) {
			return -1;
		}
		if (root->data == target->data) {
			helper(root, k);
			return 1;
		}
		//左子树
		int distance = dfs(root->lchild, target, k);
		if (distance != -1 && k >= distance) {
			if (k == distance) {
				array.push_back(root->data);
				return -1;
			}
			else {
				//在右子树中查找符合结点
				helper(root->rchild, k - (distance + 1));
				return distance + 1;
			}
		}
		//右子树
		distance = dfs(root->rchild, target, k);
		if (distance != -1 && k >= distance) {
			if (k == distance) {
				array.push_back(root->data);
				return -1;
			}
			else {
				//在左子树中查找符合结点
				helper(root->lchild, k - (distance + 1));
				return distance + 1;
			}
		}
		return -1;
	}
	void helper(tree* root, int k) {
		if (root == NULL || k < 0) {
			return;
		}
		if (k == 0) {
			array.push_back(root->data);
		}
		else {
			//递归查找符合条件的结点
			helper(root->lchild, k - 1);
			helper(root->rchild, k - 1);
		}
	}
};
int main()
{
	tree *p,*target;
	int k, val, i = 0;
	vector<int> array;
	Method m;
	p = creat();
	scanf("%d%d", &val,&k);
	target = (tree*)malloc(sizeof(tree));
	target->data = val;
	array=m.distancek(p, target, k);
	cout << array.capacity() << endl;
	while (i != array.size()) 
	{
		cout << array[i++] << " ";
	}
	cout << endl;
	return 0;
}
```

