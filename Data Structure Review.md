# Vectors

   1. What do you need to include in order to use a vector?
	#include <vector>

```
std::vector<char> v1,
	v2(5, 'a'),
	v3{'h','e','l','l','o'},
	v4(v2.begin(), v2.end()-1);
	v5(v3.begin(), v3.end()-2);
```

   2. What are the contents of `v1`, `v2`, `v3`, and `v4`?

	Empty, a a a a a, h e l l o , a a a a , h e l

   3. Write code to create `int` vectors with the following specifications:

      a) an empty vector 

	vector<int> v1;

      b) a vector containing 8 copies of the element `3` (using the fill constructor)

	vector<int> v2(0, 3);

      c) a vector containing the elements `{7, 1, 8, 9, 5, 1, 5, 0, 0, 0}` (using the initializer list constructor)

	vector<int> v3 {7, 1, 8, 9, 5, 1, 5, 0, 0, 0}

      d) a vector containing the first three elements of another vector called `v3` (using the range constructor)

	vector<int> v4(v3.begin(), v3.begin()-3);

   4. What is the output of the following statements?

      a) `std::cout << v3.at(2);`

	8

      b) `std::cout << v3[1];`

	1

      c) `std::cout << v3.front();`

	7

      d) `std::cout << v3.back();`

	0

   5. Write code using vector methods (not iterators) to produce the following outputs:

      a) print the first element of `v3`

	std::cout << v3.front();
	std::cout << v3.at(0);
	std::cout << v3.[0];

      b) print the last element of `v3`

	std::cout << v3.back();

      c) print the fourth element of `v3`

	std::cout << v3[3];

      d) print the second element of `v3`

	std::cout << v3.[1];
	
   6. Write code to fill `v1` with the elements `{2, 4, 6, 8, 10}`.

	for (int i = 1 ; i <=5; i++) v1.pushback(i*2);

   7. Write code to print out each element of `v1`.

	for (int i = 1 ; i <=5; i++) cout << v1[i];
	for (auto elt : v) cout << elt;
	for (auto it = v.begin(); it != v.end(); ++it cout << +it;

   8. What are the contents of `v1` after each of the following statements? 2,4,6,8,10

      a) `v1.push_back(11);`

	2,4,6,8,10,11

      b) `v1.insert(v1.begin()+2, 5);`

	2,4,5,6,8,10,11

      c) `v1.pop_back();`

	2,4,5,6,8,10

      d) `v1.erase(v1.end()-2);`

	2,4,5,6,10

   9. Write code to

      a) add `9` to the end of `v1`

	v1.push_back(9);

      b) add `3` as the second element of `v1`

	v1.insert(v1.begin()+1, 3);

      c) remove the last element of `v1`

	v1.pop_back();

      d) remove `3` from `v1`

	v1.erase(begin()+1);
	v1.erase(std::find(v1.begin(), v1.end(), 3))

   10. Which vector methods should you avoid using?

	insert, erase
	time complexity.

# Lists

   11. What two access methods does vector have that list does not? Why?

	at(), [] . because vectors support random access and lists do not.

   12. What two modifier methods does list have that vector does not? Why?

	push_front , pop_front  
	because operations at the begining of the list are very expensive for vectors, not for lists.

   13. Most questions that were asked for `vector` can also be asked for `list`.

# Stacks, Queues, Priority Queues
	
	#iclude <stack>
	#include <queue> priority queue as well.


   14. Create an empty `{stack, queue, priority queue}` of `ints`.

	queue<int> q;
	stack<int> s;
	priority_queue<int> pq;
	
   15. Fill the `{stack, queue, priority queue}` with the elements `{1, 2, 3, 4, 5}`.

	for ( int i = 1 ; i <= 5; i++) {
		s.push(i);
		q.push(i);
		pq.push(i);
	}

   16. Print each element of the `{stack, queue, priority queue}`. What is the output?

	while (!s.Is_empty()) {
		cout << s.top();
		s.pop();

		cout<< q.front();
		q.pop();

		cout<< qp.top();
		qp.pop();
	}

	5 1 5 
	4 2 4
	3 3 3
	2 4 2
	1 5 1


# Algorithms

   17. What do you need to include in order to use algorithms from the standard library?

	#include <algorithm>

   18. Write code using methods from `std::algorithm` to

      a) reverse the second half of a vector 

	std::reverse(v.begin()+(v.size()/2), v.end());
	std::reverse(v.begin()+((v.end()-v.begin())/2), v.end());

      b) sort a vector

	std::sort(v.begin()+v.end());

      c) reverse sort a vector

	std::reverse(std::sort(v.begin(), v.end()));
	std::sort(v.rbegin(), v.rend());

      d) find the element `5` in a list and replace it with the value `4`

	std::list<int>::iterator it = std::find(lst.begin(), lst.end(), 5)
	*it = 4;

# Iterators

   19. Write a templated function `print` to print out each element in a range.

	template <class Iter>
	void print(Iterator begin, Iterator end) {
  	for (Iterator it = begin; it != end; ++it) std::cout << *it << " ";
 		 std::cout << std::endl;
	}

   20. Write a templated function `reverse` to reverse a range.
	
	template <class Iter>
	void reverse(Iter begin, Iter end) {
	while (begin != end) {
		*begin = *end;
		++begin;
	if(begin == end) return;
	--endl
	}}

   21. Write a for loop using iterators to print each element in a vector `v`.

	......
	for (auto it = v.begin(); it != v.end(); ++it) cout << *it << " ";
	cout << endl;
	......

   22. Use an iterator to print out the third element in a vector `v`.

	Use an iterator and when it's, dereference and print. 
	cout << *(v.begin()+2);

   23. Use an iterator to increment the first element in a vector `v`.

	(*v.begin())++;

   24. Use iterators and `std::find` to print out how many elements apart `d` and `e` are in vector `v`.

	auto dit = std::find(v.begin(), v.end(), 'd');
	auto eit = std::find(v.begin(), v.end(), 'e');
	int howMany = dit - eit;
	if (howMany < 0) howMany+= -1;

   25. Use iterators and `std::find` to print out whether element `d` comes before element `e` in vector `v`.

	bool ditIsFirst = <dit < eit>;

   26. Review `iterators.cpp` carefully.

# Maps

   27. What do you need to include in order to use a map?

	#include<map>;

   28. What is the Java equivalent of `std::map`?

	TreeMap

   29. What is the Java equivalent of `std::unordered_map`?

	HashMap

   30. Declare a map `m` with a key type of `int` and a value type of `string`.

	std::map<int,string> m;

   31. `auto p = *(m.begin());`   What is the type of `p`?

	std::pair<int,string>

   32. Use `p` to print out `m`\'s first key and value.

	cout << p.first << " " << p.second << endl;

   33. Suppose `m` has the following contents: 

```
{ { 1, "cat" }, { 2, "book" }, { 3, "cello" }, { 4, "green" } }
```
   What is the value of each of the following expressions?

      a) `m[1]`

	cat

      b) `m.at(3)`

	cello

      c) `m[6]`

	""

   34. Write code to insert `5` into the map with a value of `twelve`.

	m[5] = "twelve"
	m.insert (std::make-pair(5, "twelve")
	m.insert ((5, "twelve")

   35. Write code to erase `3` from the map.

	m.erase(3);
	with find..

   36. Write code to determine if `8` is in the map, and, if it is, update its value to `Stuart`. If it is not yet in the map, insert it with a value of `Brenda`.

	map<int, string> :: iterator it = m.find(8);
	if(it != m.end()) {
	(*it).second = "stuart";
	} else {
	m.insert(8, "Brenda));
	}

   37. Review `maps.cpp` very carefully.

# File I/O

   38. Write a short program to open a file called `example.txt`, read its contents into memory, and write them back out to the end of `example.txt` (so it now contains two copies of its original contents.)

	#include <fstream>
	
	int main() {
	fstream myfile ("example.txt")
	string line;
	string lines;
	if(myFile.is.open()) {
	while(getline(myfile, line)){
		lines += getline(myfile, line);
	}
	myfile.close();
	}
	ofstream outfile ("example.txt", ios::app)
	if(outfile.is_open()) {
	outfile << lines;
	}
	}

# Exceptions

   39. Write a short program that reads in two integers from the console, tries to divide the first int by the second, throws an exception if the second int is equal to 0, and handles the exception by printing out: `Error: the denominator is 0.`

	....
	#include <iostream>
	int main() {
	try {
	int x, y;
	cin >> x >> y;
	if(y == 0) throw y;
	float z = x/y;
	} catch (int y) {
	cout << "Error";
	}
	}
	....

# Smart pointers

   40. Write code to 

      a) include the header file necessary for smart pointers

	#include <memory>

      a) declare a `shared_ptr` called `p1` pointing to a new `string` "hello"

	shared_ptr<string> p2 = p1.

      c) declare a `shared_ptr` called `p2` pointing to the same `string`

	shared_ptr<string> p2 = p1;

      d) print `p1`'s string to the console

	cout << *p1;

      e) print the length of `p1`'s string to the console

	cout << p1->length();

      f) empty `p1`
	
	p1.reset();

      g) declare a `weak_ptr` called `w1` pointing to the same `string` as `p2`

	weak_ptr<string> w1 = p2;

      h) declare a `unique_ptr` called `u1` pointing to a new string "goodbye"

	unique_ptr<string> u1(new string("gooodbye"));

   41. When will "hello"'s memory be freed?

	When p2 goes out of scope or is reset
	
   42. What is `p2`'s reference count after statement 40.c? after 40.f? after 40.g?

	2, 1, 1

   43. What error will you get from the statement `auto u2 = u1`? How can you assign `u1`'s pointer to `u2`?

	That you're trying to call unique_ptr's implicity deleted copy constructor.
	The only thing we can do is : auto u2 = std::move(u1);