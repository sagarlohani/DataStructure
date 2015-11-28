# DataStructure

Stacks:
-------

ADT : Abstract Data Type.

Operations on data type : Interface
----------------------------------
new():ADT
push(S:ADT,0:element):ADT
pop(S:ADT):ADT
top(S:ADT):element

----------------------------------


size(S:ADT):integer
isEmpty(S:ADT):boolean

----------------------------------

public interface Stack{
	
	public int size();
	public boolean isEmpty();
	public Object top() throws StackEmptyException;


	public void push(Object element);
	public Object pop() throws StackEmptyException;

}

Array based stack

public class ArrayStack implements Stack{
	
	public static final int CAPACITY = 1024;

	private int N;
	private Object S[];
	private int t = -1;
	
	public ArrayStack(){
		this(CAPACITY);
	}

	public ArrayStack(int cap){
		N = cap;
		S = new Object[N];
	}

	public int size(){
		return(t +1);
	}

	public boolean isEmpty(){
		return (t <0);
	}

	public void push(Object obj) throws StackFullException{

	if(size == N) throw new StackFullException("Stack Overflow");

	S[++t] = obj;

	}

	public Object top() throws StackEmptyException{
		if(isEmpty()) throw new StackEmptyException("Stack is Empty");
		return S[t];
	}

	public Object pop() throws StackEmptyException{
		Object elem;
		if(isEmpty()) throw new StackEmptyException("Statck is Empty");
		elem = S[t];
		S[t--] = null;
		return elem;
	}

}

