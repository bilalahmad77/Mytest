#include <iostream.h>
class linklist
{
private:
struct node
{
int data;
node *link;
}*p;

public:
linlist();
void addatbeg(int num);
void reverse();
void display();
int count();
~linklist();
};

linklist::linklist()
{
p=NULL;
}

void linklist::addatbeg(int num)
{
node *temp;
temp=new node;
temp->data=num;
temp->link=p;
p=temp;
}
void linklist::reverse()
{
node *q,*r,*s;
q=p;
r=NULL;
while(q!=NULL)
{
s=r;
r=q;
q=q->link;
r->link=s;
}
p=r;
}

void linklist::display()
{
node *temp=p;
cout<<endl;

while(temp!=NULL)
{
cout<<temp->data<<" "; 
temp=temp->link;
}
}

int linklist::count()
{
node *temp=p;
int c=0;
while(temp!=NULL)
{
temp=temp->link;
c++;
}
return c;
}

linklist::~linklist()
{
node *q;

while(p!=NULL)
{
q=p->link;
delete p;
p=q;
}
}

void main()
{
linklist list;
list.addatbeg(8);
list.addatbeg(44);
list.addatbeg(18);
list.addatbeg(4);
list.addatbeg(24);
list.addatbeg(6);

cout<<"\n Elements in list before reversing:";
list.display();

cout<<"\n Elements in list after reversing:";
list.display();
}
