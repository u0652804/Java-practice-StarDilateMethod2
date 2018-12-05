# Java-practice-Print "a1" ~ "z1"

### Problem
有一String為"a,b,c,d,e,f,g..."，請分別列印出"a1"、"b1"、"c1"...

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

