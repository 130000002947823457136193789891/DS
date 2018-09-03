#ifndef ADJLIST_UNDIR_GRAPH_H    //邻接表实现有向图

#define ADJLIST_UNDIR_GRAPH_H

#include "AdjListDirGraphArc.h"

#include "AdjListDirGraphVex.h"

#include <iostream>

using namespace std;

#define DEFAULT_SIZE 10



enum VisitStatus{VISIT,UNVISIT};



//有向图邻接表类定义

template<typename ElemType>

class AdjListDirGraph     

{

public:

	//函数成员:

    AdjListDirGraph(int _vexMaxNum=DEFAULT_SIZE);   //无参构造函数

	AdjListDirGraph(ElemType *Vexs,int _vexNum,int _vexMaxNum=DEFAULT_SIZE);   //有参构造函数

	~AdjListDirGraph();   //析构函数

	void Clear();   //清空所有弧

	bool isEmpty();   //判断有向图是否为空

	ElemType GetElem(int vex);    //获取顶点元素值

	int GetOrder(ElemType &e);    //获取顶点的序号

	void InsertArc(int vex1,int vex2);     //插入弧

	void InsertVex(ElemType &e);     //插入顶点

	void DeleteArc(int vex1,int vex2);     //删除弧

	void DeleteVex(ElemType &e);     //删除顶点

	int GetVexNum();     //获取有向图的顶点个数

	int GetArcNum();     //获取有向图的弧数个数

	int FirstAdjVex(int vex);     //获取有向图中顶点vex的第一个邻接点

	int NextAdjVex(int vex1,int vex2);     //获取有向图中顶点vex1的相对于vex2的下一个邻接点

	void Display();     //显示有向图



private:

	//数据成员:

	VisitStatus *tag;

	AdjListDirGraphVex<ElemType> *vexTable;

	int vexNum;

	int vexMaxNum;

	int arcNum;



};
