# RealTimeFriendlySTL
Some Data Structures and Algoirhtms 



This project provides STL competible data structures and algorithms
These ones are real time friendly
	Soft Real Time System 
	However, we are writting this out in Big O

		Indivual Times depend on several factors:
			1. perodicity => worest day of the week
			2. geopgraphical spread 
			3. Desgin of computer itslef
		So instead, we will include computional complexity 
			Write those in as our own requirments
		
		We are not going to overpromsise 
			
			

To do this, we have the following:
	stack memory or static memory favored over dynamic for the containers
	Intrunsive Data Structures
	"Containers" and memory ownership

The STL is a very handy library 
It has iterators, containers and algorihtms 

However, I know one of the issues with the STL is the iterator acess names
For example, they seem to be based entierly on sequnce containers
Graph theroy => face an issue wtih begin() and rbegin()

What I am doing instead:
	c_leftward_begin() c_leftward_end() => forwards iteration 
	c_rightward_begin() c_rightward_end() => reverse iteration

	Graph Theroy Iteration

	c_preorder_begin() c_preorder_end() => Preorder traversal 
	c_postorder_begin() c_postorder_end() => Postorder traversal 
	c_inorder_begin() c_inorder_end() => In-Order traversal 


	The c prefix is just like from STL -> that one is not change data through iterator
	For changing the data as iterating, it also has the ones without c_
		Ananologous to STL 
	
	preorder, postorder, inorder for graph theroy 
		12 procedure names

	The c writtern before is just like from STL -> that one is not change data through iterator
	There is also one without c in it 


 Iterators
	These are strongly conforming with STL 
	Also execption safe code => yes, but we have a stronger gaurantee than strong exection garuantee
	We have no throw, but just on iterators
		Rest of the program may 
		Ofcourse, you can, question about may 

	Specifically,

		they are std::forward iterator with strong-multi-pass garuantee
		Also assignable iterators

		
		Passed / Copyed as values:
			Example: 2 primative types and a refrence
					1 primative types and a refrence



		swap Procedure 
		Execptions: No Throw
			Computional Complexity
				Time: O(1)
				Space: O(1)


		!= Operator
			Execptions: No Throw
			Neither by value equivalance or by identity
			Also same type
			If iterating on same data structure and advanced same amount
			Computional Complexity 
				Time: O(1)
				Space: O(1)

		== Operator 
			Execptions: No Throw 
			negation of before
				Time: O(1)
				Space: O(1)
		

		Assigment Operator
			Execptions: No Throw 
			To borrow terminology from const, there is deep const and shallow const
			Iterator assigned to iterate on that data structure 
				Example: 2 diffrent dynamic arrays
			It is at same advace as the other one
			Computional Complexity
				Time: O(1)
				Space: O(1)



		End of a pass without assigment, they just stay with repated calls
			Idenpotent Operation => further procedure calls do nothing 

		prefix increment and postfix increment
			return a copy that is
				advanced to next if not at end
				same otherwise
			Idenopotent Operation 
				Even though, yes that is a copy 


	Assigment on iterators
		Move to same spot on that data structure
		Valid to be another data structure of same type

	Example Usage:
					
	if (it1 == it2) {
		 ++it1;
		 ++it2;
	     assert(it1 == it2); // has to hold for multi-pass sequences, which it does
	}


	Which it does. 
	When at the end of the pass, the it1 == end
	it2 would also == it1

	The == on iterators 
		a) same data structure (not just kind)
		b) advanced to same spot on data structure 

				
		
Operators not ordinary procedures / methods
For operators in C++,  We are allowed to pick the return type in C++ to be by value
Which considering these are very lightweight (ex. 2 primatives with a refrence)

But they aren't pointers beacuse they can not be in some situations
	Example: Heap Data Structure 

	
	
	

	RAII / Stack memory for efficnet fool proof memroy
	Static if it is not way too much for static 
		Dynamic could also be done easily, but I suspect the stack would be more efficent
		For example, spike on plot over time

	"Containers" and items stored in them 
		the containers have strong aggegeration with items
		deletion with container going out of scope 

	Intrunsive Data Structures
		the temporary internal struct can be constructed by the conainter
		We are trying to avoid suprising spikes on the plots 

	On Amortized Anaylisis
		While we may do amortized anyalsis
		Strong Garuantee vs weaker vs etc. provided by the library
			Various extents / writting
		
		One intersting example is std::vector
			does geometric series rather than  arthmatic series

		
	Exception Throwing Stuff
		Constructors are non-throwing
		static builder method returns Mabye 
			Like std::opitional, need an applicative
		Destructors are non-throwing
		Procedures are either strong or non-leaking  or no throw 
			No Throw 
				just things within that class or struct being passed as a paramter
				yes, our iterators are No Throw 
			Strong is either same state as before or changed to targert state
				Procedures in data structure state this 
			non-leaking is that invaraints of data structure kept as well as resource leaks not occur
				
		Sources of execptions thrown:
			Outside of this code / project 
			This project itself doesn't
			

	Pre Conditions and Post Conditions
		Procedures / member functions / non-member functions come in two seperate kinds:
		Unchecked say thier preconditoins before run and postconditions
		Checked check the preconditions before run and state what happens when they are not meet
		
			
		For the checked preconditoins / postconditions 
		a) Nothing / No-Op
		b) assertion => crash
		c) optional / maybe in the return type 
		
		Of course, we try avoid the unchecked procedures entierly
		We have iterators and strong types 
				These iterators may help 

	
			

	Functors 
		pass this as a template
		provide own call operator on a struct
		Passed on stack 
		Comments will say the static types expects 

		std::function provides a type signature for it
			However, that one forces it to be stack
		Function Pointers
			I actually disagree with those who state that using function pointers would be less
			I believe that this is one of the few times C++ beats C 



Version of C++ using:
	We are using C++14



	

