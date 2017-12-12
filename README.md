# 20161104596
链表
#include"iostream"
using namespace std;
struct student
{
	char name[5];
	char num[15];
	int age;
	struct student * next;
};
int main()
{
	struct student *p,*q,*head;
	int a=1;
	head=new student;
	q=head;
	p=q;
	cout<<"请输入学生姓名    ";
	cin>>p->name;
	cout<<"请输入学生学号    ";
	cin>>p->num;
	cout<<"请输入学生年龄    ";
	cin>>p->age;
	while(cout<<"继续输入1 or 2"<<endl,cin>>a,a==1)
	{
		p=new student;
		q->next=p;
		q=p;
		cout<<"请输入学生姓名    ";
		cin>>p->name;
		cout<<"请输入学生学号    ";
		cin>>p->num;
		cout<<"请输入学生年龄    ";
		cin>>p->age;
		p->next=NULL;	 
	}
	p=head;
	while(p!=NULL)
	{
		cout<<p->name<<" "<<p->num<<" "<<p->age<<endl;
		p=p->next;
	}
	p=head;
	do
	{
		q=p->next;
		delete p;
		p=q;
	}
	while(q);
	return 0;
}
