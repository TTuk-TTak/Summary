자료형 알아보기
// 라이브러리
#include <typeinfo>

// 사용
cout << typeid(a).name();
* string에서 원소idx로 하나씩 접근한다면 그 원소 하나는 -> char 





char 문자열 
// 라이브러리 포함 
#include<cstring>

// strcmp 함수 
strcmp(a,b)
* char 한글자는 == 으로 비교 ! 

string 함수
// erase
str.erase(시작위치, 크기)
str.erase(str.begin() + 2)	// 특정위치의 문자 지우기 (char pointer 이용해)
str.erase(str.begin(), str.begin()+2)	// 특정범위의 문자지우기

// insert
str.insert(시작위치, 추가할 문자열)

// append
str.append(추가할 문자열)	// 제일 뒤에 따라붙음 // char 안되고 string 만됨






SubString, Parsing
string a = "hihihihi";

// find
a.find(찾을 string, 시작위치);

// substr 사용
a.substr(시작위치, 크기);

// replace 사용
a.replace(시작위치, 길이, 치환할문자열)
//ex)
	int a = 0;
	while (1) {
		a = new_id.find("..", a);
		if (a == -1)
			break;
		new_id.replace(a, 2, ".");
		
	}








vector iterator
// iterator
for(auto it = v.begin(); it != v.end(); it++)
	cout<< *it;
* vector는 erase, 또는 pop 연산이 일어날 시, 크기가 바뀌므로, 원소idx 접근 보다는 auto로 접근! 

vector iterator + erase 
=> erase를 진행할 땐, 전체 크기 size가 바뀌므로 조심해줘야 한다!! 

	for (auto it = v.begin(); it != v.end();) {	// it++을 하지 않고 기다림 
		if (!checke(*it)) 
			it = changed.erase(it);	// 지우고, 순환자를 다음 위치로 참조해줘야함. 
		else
			it++;	// 지우는 일이 없을 때만 ++
	}


2차원 vector
// 2차원 vector를 size와 함께 지정
vector<vector<int>> graph(size, vector<int>(size,0));

map
// 라이브러리 포함
#include <map>

// 선언
map<string, int> match;

// 삽입
map.insert(pair("hi",1));
map.insert(make_pair("hi",1));

// 값 찾기
map.at("hi");	// key값을 넣음
순열 next_permutation 
 => 모든 경우의 수 다 출력해줌 

  vector자체의 값을 재정렬 해줌 . 

  *** do-while로 안하고 그냥 while로 하면, 원래의 vector값은 빼고 나오므로 주의 !! ***

#include<algorithm>
...

    do{
        
        for(int i=0;i<weak.size();i++){
            cout<<weak[i]<<" ";
        }
        cout<<"\n";
    }while(next_permutation(weak.begin(), weak.end()));
 ...


최소값 min
 => a,b 중에 더 작은값을 최솟값으로 저장함 

int m = min(a,b);




SORT
=> vector를 sort 함

sort(vector.begin(), vector.end(), -)


isdigit
=> 숫자인지 check 해주는 함수 
