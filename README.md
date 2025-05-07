#include <iostream>
using namespace std;
class Animal
{
private:
	string name;
public:

	void setName(string name)
	{
		this->name = name;
	}
	string getName()
	{
		return name;
	}
	void echo()
	{
		for(int i=1;i<=3; i++)
		{
			cout << name << endl;
		}

	}
};
int main()
{
	setlocale(LC_ALL, "Russian");
	Animal ani;
	ani.setName("Шарик");	
	ani.echo();
	return 0;
	
}
