#include <iostream>
using namespace std;
class listnode{
public:
string first_name,last_name;
long long int phone_number;
listnode* next;
listnode*prev;
listnode(string first_name,string last_name,long long int data){
    this->first_name=first_name,this->last_name=last_name,this->phone_number=data,this->next=NULL,this->prev=NULL;
}
void delete_contact(listnode*&dummy,string first_name,string last_name){
    listnode*temp=dummy;
    while(temp!=NULL){
        if(temp->first_name+temp->last_name==first_name+last_name){
            temp->prev->next=temp->next;
            temp->next->prev=temp->prev;
            free(temp);
            return;
        }
        temp=temp->next;
    }
    cout<<"There is no such name"<<endl;
    return;
}
void display_contacts(listnode*dummy){
    listnode*temp=dummy;
    if(temp==NULL){
        cout<<"There are no contacts saved"<<endl;
        return;
    }
    while(temp!=NULL){
        cout<<temp->first_name+temp->last_name<<" "<<temp->phone_number<<endl;
        temp=temp->next;
    }
    return;
}
void search_contact(listnode*dummy,string first_name,string last_name){
    listnode*temp=dummy;
    while(temp!=NULL){
        if(temp->first_name+temp->last_name==first_name+last_name){
            cout<<temp->phone_number<<endl;
         return;
        }
        temp=temp->next;
    }
    cout<<"No results found"<<endl;
    return;
}
void create_new_contact(string first_name,string last_name,long long int data,listnode*&dummy){
    listnode*temp=new listnode(first_name,last_name,data);
    listnode*a=dummy;
    if(dummy==NULL){
        dummy=temp;
        return;
    }
    while(a->first_name+a->last_name<first_name+last_name && a!=NULL){
        if(a->next==NULL){
            temp->prev=a;
            a->next=temp;
            break;
        }
        if(a->next->first_name+a->next->last_name>first_name+last_name){
            temp->next=a->next;
            a->next=temp;
            temp->prev=a;
            temp->next->prev=temp;
        }
        a=a->next;
        }
        if(a->first_name+a->last_name>first_name+last_name){
            temp->next=a;
            a->prev=temp;
            dummy=temp;
        }
        return;
    }  
};
int main()
{
    listnode*contacts;
    listnode*phone_book;
   while(1){
    cout<<"want to go back -> press (0)"<<endl;
    cout<<"To add contacts -> press (1)"<<endl;
    cout<<"search contacts -> press (2)"<<endl;
    cout<<"display contact -> press (3)"<<endl;
    cout<<"delete contact  -> press (4)"<<endl;
    int choice;
    string first_name,last_name;
    long long int phone_number;
    cin>>choice;
    if(choice==0){
        break;
    }
    switch(choice){
        case(1):{
        cout<<"enter details"<<endl;
        cin>>first_name>>last_name>>phone_number;
        phone_book->create_new_contact(first_name,last_name,phone_number,contacts);
        break;}
        case(2):
        cout<<"enter details"<<endl;
        cin>>first_name>>last_name;
        phone_book->search_contact(contacts,first_name,last_name);
        break;
        case(3):
        phone_book->display_contacts(contacts);
        break;
        case(4):
        cout<<"enter details"<<endl;
        cin>>first_name>>last_name;
        phone_book->delete_contact(contacts,first_name,last_name);
    }
   }
}
