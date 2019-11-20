public class LinkList{ //链表
    public Node head; //对第一个节点的引用
    public Node current;  //对下一个节点的引用
    public Node temp;  //

    public void add(int data){ //初始化每个节点
        if(head == null){ //如果链表结构不存在
            head = new Node(data); //初始化第一个节点
            current = head; //引用指向本节点在只有一个节点的情况下
            current.forward = null;
            current.index = 0;
        }else{
            temp = current;
            current.next = new Node(data); //把本节点类中的成员变量next设为对下一个节点的引用
            current = current.next; //指向下一个节点
            current.forward = temp;
            current.index = temp.index + 1;
        }
    }

    // 排序输出
    public void print(Node node){
        if(node == null){
        return ;
        }

        while(node != null){
            System.out.print(node.data+" ");
            node = node.next; //最后一个Node的next没有new 所以为null
        }
    }

    private Node getLastNode(Node node)
    {
        if(node == null){
            return null;
        }

        while(node.next != null){
            node = node.next; //最后一个Node的next没有new 所以为null
        }
        return node;
    }

    private Node getLastNodeValueNoZero(Node node)
    {
        if(node == null){
            return null;
        }

        while(node.next != null){
            node = node.next; //最后一个Node的next没有new 所以为null
        }
        while ((node.data == 0) &&(node.forward != null))
        {
            node = node.forward; //最后一个Node的next没有new 所以为null
        }
        return node;
    }

    private void SetLastNodeValue(Node node,int value)
    {
        if(node == null){
            return;
        }
        node.data = value;

        while(node.next != null){
            node = node.next; //最后一个Node的next没有new 所以为null
            node.data = value;
        }
    }
    public void dealTheTask(Node node)
    {
        long number = 0;
        int outindex = 20;
        Node LastNode;
        Node TempNode;
        if(null == node)
        {
            return;
        }

        node = getLastNode(node);
        LastNode = node;
        while ((node.data > -1) || (node.forward!= null))/*not the last line*/
        {
/*            TempNode = LastNode;
            while ()
            {
                for(int k = 0;k<TempNode.data;k++)
                {
                    System.out.print("* ");
                }
            }*/
            if(node.index < outindex)
            {
                System.out.println(node.index);
                outindex = node.index;
            }
            number += node.data;
            number ++;
            node.data=0;
            if (node.forward!= null)
            {
                node = node.forward;
            }

            //if(node.data > 0)
            {
                node.data--;
                SetLastNodeValue(node,node.data);
                if(node.data > 0)
                node = getLastNodeValueNoZero(node);
              /*  if (node.forward== null)
                {
                    node.data--;
                    SetLastNodeValue(node,node.data);
                    node = getLastNodeValueNoZero(node);
                    if(node.data ==0)
                    {
                        number++;
                        break;
                    }
                }*/

            }


        }
        System.out.println(number);
    }

    // 定位索引的位置
    public void posIndex(int index) {
        if (head == null) {
        return;
    }

    if (index == -1) {
        return;
    }

    current = head;
    int j = 1;
    while (current != null && j < index) {
            current = current.next;
            j++;
        }
    }


    class Node{ //链表中每个节点的数据存储类
        int data; //数据域
        int index;//指针序列号
        Node next; //下一个指针
        Node forward; //上一个指针

        public Node(int data){
        this.data = data;
        }
    }

    public static void main(String[] args){
         int index;
           index = 20;
           LinkList list = new LinkList();
           for(int i =0;i<index;i++){
               list.add(index);
           }
           list.dealTheTask(list.head);
    }
}
