# MyButton 클래스 설명

## 개요
UIView를 사용하여 UIButton과 흡사한 동작을 수행하는 버튼 컨트롤 클래스를 만들어봅니다. 대체적인 설명과 예는 [UIButton 문서](https://developer.apple.com/documentation/uikit/uibutton)와 [UIControlState 문서](https://developer.apple.com/documentation/uikit/uicontrolstate)를 참고하면 좋습니다.

## 간략 설명
* UIView를 상속받습니다
* 텍스트를 표현할 수 있는 레이블과 배경 이미지를 표현할 수 있는 이미지뷰를 갖습니다.
* UIButton의 버튼 스타일은 따로 없어도 됩니다(system, custom, infoDark... 등)
* 버튼은 상태에 따라 상태값을 갖습니다
	* highlighted
		* 사용자가 버튼을 누르고 있는 상태
	* disabled
		* 비활성화 상태
	* normal
		* 평소 상태
	* selected
		* 선택된 상태
* 버튼의 상태값은 여러 형태로 조합될 수 있습니다.
	* normal + highlighted, selected + highlighted, normal + disabled, selected + disabled ...
	* normal 상태와 selected 상태는 동시에 표현될 수 없습니다.
	* disabled 상태일 때에는 현재 상태에서 비활성화 되었다는 시각적 표현만 하면 됩니다. 또한, 버튼을 선택해도 아무 동작하지 않는 비활성화 상태가 되어야합니다.
* 각각의 상태에 따라 레이블의 텍스트와 이미지뷰의 이미지를 표현할 수 있어야 합니다.
* 여러 액션(target과 selector)를 가질 수 있습니다.
	* 액션은 기본적으로 touch up inside 이벤트에 동작하도록 합니다.
	* 여러 이벤트를 구분하여 액션을 수행하여도 좋습니다.


## 동작 영상
* [enable / disable, highlighted, nomal / selected](../video/my_button.mov)
* [multiple action](../video/my_button_2.mov)


## 해결실마리
* 필수 해결실마리
	* UIView, touchesBegan, touchesEnd
* 선택 해결실마리
	* UIControlState, delegation / Notification, NotificationCenter / Selector, UITapGestureRecognizer