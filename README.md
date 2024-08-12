// # linked_list


class Main {
    static Node head=null;
    static void add_last(int x){
        if(head==null){
            Node n = new Node(x);
            head=n;
        }
        else{
            Node n =new Node(x);
            Node ptr=head;
            while(ptr.next!=null){
                ptr=ptr.next;
            }
            ptr.next=n;
        }
        
    }
    static void print(Node head){

          Node ptr=head;
        while(ptr!=null){
            System.out.print(ptr.data+" -> ");
            ptr=ptr.next;
        }
        System.out.println();
        System.out.println("===========================");
    }
   
    static void add_phele(int num){
        if(head==null){
            Node n = new Node(num);
            head=n;
        }
        else{
            Node n =new Node(num);
            n.next=head;
            head=n;
        }
    }
    static void add_middle_insert(int data,int pos){
        Node num=new Node(data);
        if(pos==0){
            num.next=head;
            head=num;
            
        }
        else{
        Node var=head;
        for(int i=0; i<pos-1; i++){
            var=var.next;
        }
        num.next=var.next;
        var.next=num;
        }
    }
    static void delete_element(int pos){
        Node num =new Node(pos);
        if(pos==0){
            head=head.next;
        }
        else{
            Node var=head;
            for(int i=0; i<pos-1; i++){
                var=var.next;
            }
          var.next=var.next.next;
        }
    }
    
static Node reverse(){
        Node curr=head;
        Node prev=null;
        while(curr!=null){
            Node temp=curr.next;
            curr.next=prev;
            prev=curr;
            curr=temp;
        }
        return prev;
    }
    
static void delete_name(int data){
    Node n =new Node (data);
    if(head.data==n.data){
        head=head.next;
    }
    else{
        Node var=head;
        while(var.next.data!=n.data){
            System.out.println("==");
            var=var.next;
        }
        var.next=var.next.next;

    }
}
    
    public static void main(String[] args) {
        add_last(12);
        add_last(15);
        add_last(18);
        add_last(20);
        add_last(25);
        add_last(50);
        print(head);
        // add_middle_insert(500,0);
        // print();
        // delete_element(2);
        // print();
        // delete_element(3);
        // print();
    //  Node temp=reverse();
    //   print(temp);
      
      delete_name(12);
      print(head);
        
    }
}

class Node{
    int data;
    Node next; // reference variable
    Node(int data){
        this.data=data;
    }
}
