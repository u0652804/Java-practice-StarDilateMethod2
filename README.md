# Java-practice-StarDilateMethod2

### Problem
請用程式畫出下列圖型

![demo](/image/demo.png)

### output
![demo](/image/demo.png)

### Java code
		
		String str = "";
		
		// init. str = "a,"~"z,"
		for(char i = 'a'; i <= 'z'; i ++)
			if(i == 'z')
				str = str + i + ' ';
			else
				str = str + i + ',';
			
		System.out.print("The String : " + str + "\n");
			
		System.out.println("print as below : ");
		// print a1 b1 c1...
		for(int i = 0; i < str.toCharArray().length; i += 2)
			System.out.println(str.charAt(i) + "" + '1');

