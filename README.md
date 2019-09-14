# manual
* GetDlogItemInt () 및 SetDlgItemInt를 가진 한 덧셈 계산기 <br><br>
1)비주얼 스튜 2019를 실행한다.<br>
2)새 프로젝트 만들기를 클릭한다.<br>
3)검색 할 수 있는 곳에 mfc를 치고 검색 결과로 나온 mfc앱을 더블 클릭한다.<br>
4)프로젝트 이름은 어떠한 것으로 해도 상관 없으며 임의로 설정을 한다.(예:clr1)<br>
5)프로젝트 이름을 적었으면 만들기를 누른다.<br><br>
6)애플리케이션 종류를 정해야 하는데 아래쪽 화살표 모양을 눌러 대화상자 기반을 눌러준다.<br><br>
7)대화상자 기반으로 바꿔 줬다면 마침을 누른다.<br><br>
8)떠 있는 화면에서 왼쪽 혹은 오른쪽에 솔루션 탐색기가 있을텐데 리소스 파일이라고 적힌 곳 왼쪽에 작은 화살표 모양을 누르고
  설정한이름.rc라고 되어 있는 것을 더블 클릭 해준다.<br><br>
9)더블 클릭을 하고 Dialog를 눌러 파일을 열어준 후 IDD_설정한이름_DIALOG를 더블클릭 해준다.<br><br>
10)잘 작동 되는지 확인 하기 위해 위쪽에 녹색 화살표로 로컬 windows 디버거란 부분을 눌러 창이 뜨는지 확인 한후<br>
   만약 창이 안뜬다면 ctrl+alt+del를 눌러 프로그램을 끈 후 다시 설정을 해준다.<br><br>
11)클릭을 해준 후 왼쪽 혹은 오른쪽 가장 끝에 도구 상자라 적힌 부분이 있는데 그것을 클릭해 열어준 후 Edit Control이라고 적힌 것을
   클릭 한 후 중앙에 위치한 조그만 창에 놓는다.<br><br>
12)3개 정도를 놓아두고 TODO:여기에 대화 상자 컨트롤을 배치합니다 란 부분은 우클릭하여 잘라내기를 선택해 지워 준다.<br><br>
13)Edit Control을 3개 놓아 두었다면 다시 도구 상자를 열어 Button을 놓고 Button 아래 나머지 Edit Control을 놓아둔다.<br><br>
14)놓아둔 Button을 누른 후 도구상자를 열었던 곳을 보면 속성이라고 적힌게 있는데 그것을 누르면 여러 목록이 나오는데
   모양 부분에서 Caption에 보면 Button1이라고 나와 있을텐데 누르게 되면 이름을 바꿀 수 있다.<br><br>
15)Button1을 지우고 +로 바꿔주고 엔터를 치면 창에 옮겨놓은 Button1이 +로 바뀐다.<br><br>
16)+로 바뀐 부분을 더블 클릭하면 소스 코드를 칠 수 있는 창이 뜨는데 여기서 void 설정한이름Dlg::OnBnClickButton1()이라고 적힌곳
   중괄호 안에 int a= GetDlgItemInt(IDC_EDIT1);//은 맨 위의 Edit Control에 숫자를 넣을수 있게 해준다.<br>
              int b= GetDlgItemInt(IDC_EDIT2);//은 맨위의 Edit Control의 바로 밑의 Edit Control에 숫자를 넣을 수 있게 해준다.<br> 
              int c= a+b;//위의 두 Edit Control에 넣은 값을 합해서 나오는 숫자를 출력해준다.<br>
              SetDlgItemInt(IDC_EDIT3,c); 을 쳐 준다.<br><br>
17)그리고 로컬 windows 디버거를 누르거나 키보드에서 F5를 누르면 실행이 되고 맨위의 Edit Control에 임의의 숫자를 넣고
  그 아래 Edit Control에도 임의의 숫자를 넣은 후 +버튼을 누르면 두 숫자의 합이 맨 아래의 Edit Control에 나오게 된다.<br><br><br>
* 에디트 컨트롤에 정수 변수를 추가하고, UpdateData() 함수를 활용하여 계산기 만들기<br><br>
1) 처음 설정부분은 GetDlogItemInt () 및 SetDlgItemInt를 가진 한 덧셈 계산기의 1)에서 15)까지의 내용과 같기에 위의 내용 참조.<br><br>
2) Edit Control 중 맨위의 것을 선택해 오른쪽 클릭을 해주고 클릭 했을 때 뜨는 창에서 변수 추가하기 하는 부분을 클릭해준다.<br><br>
3) 클릭했을 때 뜨는 목록중 범주 부분을 값으로 바꿔주고 이름 부분은 m_a, 변수 형식은 int로 바꿔주고 마침을 누른다.<br><br>
4) 나머지 두 Edit Control도 같은 형식으로 m_a로 바꿔준 Edit Control 밑의 Edit Control은 m_b로 나머지 Edit Control은
   m_c로 바꿔준다.<br><br>
5)+버튼을 더블클릭해 소스를 입력 할 수 있는 창을 띄우고 void Cclr77Dlg::OnBnClickedButton1()부분의 중괄호 안에
  UpdateData(true);<br>
  m_c = m_a + m_b;<br>
  UpdateData(false);<br>
  을 넣어주고 키보드의 F5를 눌러 실행 시킨다.<br><br>
6)결과 창이 뜨고 맨위의 Edit Control에 임의의 숫자를 넣고 그 아래 Edit Control에도 
  임의의 숫자를 넣은 후 +버튼을 누르면 두 숫자의 합이 맨 아래의 Edit Control에 나오게 된다.<br><br><br>
*초록색의 굵기가 16픽셀인 마우스 왼쪽 버튼을 누르고 글씨를 작성할 수 있는 다이얼로그 기반의 펜 만들기<br>
1)visual studio 2019를 실행 시킨다.<br><br>
2)새 프로젝트 만들기를 클릭한다.<br><br>
3)검색 할 수 있는 곳에 mfc를 치고 검색 결과로 나온 mfc앱을 더블 클릭한다.<br><br>
4)프로젝트 이름은 어떠한 것으로 해도 상관 없으므로 임의로 설정을 한다.(예:pen7)<br><br>
5)프로젝트 이름을 적었으면 만들기를 누른다.<br><br>
6)애플리케이션 종류를 정해야 하는데 아래쪽 화살표 모양을 눌러 대화상자 기반을 눌러준다<br><br>
7)대화상자 기반으로 바꿔 줬다면 마침을 누른다.<br><br>
8)떠있는 화면에서 왼쪽 혹은 오른쪽에 솔루션 탐색기가 있을텐데 리소스 파일이라고 적힌 곳 왼쪽에 작은 화살표 모양을
  누르고 설정한이름.rc라고 되어있는 것을 더블 클릭 해준다.<br><br>
9)더블클릭을 하고 Dialog를 눌러 파일을 열어준 후 IDD_설정한이름_DIALOG를 더블클릭 해준다.<br><br>
10)잘 작동이 되는지 확인 하기 위해 위쪽에 녹색 화살표로 로컬 windows 디버거란 부분을 눌러 창이 뜨는지 확인한 후 
  만약 창이 안뜬다면 ctrl+alt+del를 눌러 프로그램을 끈 후 다시 설정 해줍니다.<br><br>
11)중앙에 있는 조그만 창에 마우스를 갖다대고 왼쪽클릭은 한번 해준후 맨오른쪽에 속성이라고 적힌 부분을 클릭한다.<br><br>
12)클릭하면 속성 창이 뜨고 여려 목록이 뜨는데 그중 그림이 있는 부분(아이콘)에서 왼쪽에서 4번째 그림에 마우스를 갖다대면
  메시지라고 뜨는데 그것을 왼쪽클릭 한번을 한다.<br><br>
13)그 후 WM_MOUSEMOVE를 찾아 좌클릭을 한번 해주면 바로 오른쪽에 조그만 아래쪽을 향한 화살표모양이 나오는데 눌러주면
  <Add>OnMouseMove라고 나오는데 그것을 클릭 해준다.<br><br>
14)클릭을 하면 소스를 넣을 수 있는 창이 뜨는데 void Cpen99Dlg::OnMouseMove(UINT nFlags, CPoint point)부분 중괄호안에
  소스를 넣어 주면 된다.<br><br>
15)void Cpen99Dlg::OnMouseMove(UINT nFlags, CPoint point)바로 위에 CPoint pnt;를 쳐 주는데 이는 cpoint 변수를
  보다 넓게 사용하기 위해 적어 주는것이다.<br><br>
16)그리고 if (nFlags == MK_LBUTTON) {<br>
	CClientDC dc(this);<br>
                CPen pen(PS_SOLID, 16, RGB(0, 255, 0));//펜의 색깔(스타일,크기,색상)<br>
                dc.SelectObject(&pen); <br>
		dc.MoveTo(pnt);<br>
		dc.LineTo(point);<br>
	}<br>
	pnt = point;<br>
	CDialogEx::OnMouseMove(nFlags, point);<br>
  을 써넣어 준다.<br><br>
17) 실행을 위해 키보드의 F5를 누르고 실행 되면 빈 창이 하나 뜨는데 마우스 좌클릭을 누른 상태에서 이리저리 움직이면
  펜처럼 선이 그어진다.<br>


