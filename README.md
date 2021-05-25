//SystemFixer Main
//2021/5/16 17:25 
//by Timmy 
#include<iostream>
#include<windows.h>
#include<iomanip>
using namespace std;
int main(){ //main()
	//Loading Fixer Files
	cout<<"SystemFixer 4.5 主程序"<<endl;
	cout<<"======================"<<endl;
	int m,s;
	cout<<"1.使用sfc工具修复"<<endl;
	cout<<"2.使用Dism工具修复"<<endl;
	cout<<"3.查看使用说明"<<endl;
	cout<<"4.退出该程序" <<endl;
	cout<<"请输入您的选择:";
	cin>>m;
	if(m==1){
		cout<<"1.使用scannow扫描方式"<<endl;
		cout<<"2.使用VERIFYONLY扫描方式(快)"<<endl; 
		cout<<"请输入sfc扫描方式:";
		cin>>s;
		if(s==1){
		    cout<<"正在启动修复程序..."<<endl;
			system("sfc /scannow");
			cout<<"修复成功，按任意键继续";
			system("pause>nul");
			return 0;
		}else if(s==2){
			cout<<"正在启动修复程序..."<<endl;
			system("sfc /VERIFYONLY");
			cout<<"修复成功，按任意键继续";
			system("pause>nul");
		}else{
			cout<<"输入的序号不是可用操作,按任意键继续"<<endl;
			system("pause>nul");
			return 0; 
		}
	}else if(m==2){
		cout<<"正在启动修复程序..."<<endl;
		Sleep(0.5);//Sleep 0.5 seconds
		system("Dism /Online /Cleanup-Image /CheckHealth");
		system("Dism /Online /Cleanup-Image /RestoreHealth");
		//Fix the system
		cout<<"修复完成，按任意键继续";
		system("pause>nul");
		//Press any key to continue
		return 0; 
	}else if(m==3){
		system("cd lib");
		system("eula.txt");
		system("echo User.Time:%random% Name:Setups>>eula.txt.temp");
		cout<<"操作成功完成，按任意键继续";
		system("pause>nul");
		return 0; 
	}else if(m==4){
		return 0;
	}else{
		cout<<"输入的序号不是可用操作,按任意键继续"<<endl;
		system("pause>nul");
		return 0;
	}
}
//For Windows 10
//
