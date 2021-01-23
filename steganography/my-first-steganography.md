so in this we got two images ```blueprint.jpg  ``` and ```blueprint0.jpg ``` so from the question we can conclude that the images have been embedded with some msg
our goal is to reavel that msg
 
so we can go to the tool ```steghide ```  we can use ```steghide extract -sf blueprint.jpg ``` and we can get the a file in which we can see some text ``` d4rk_s1d3 ``` which is password so we should use this password ``` steghide extract -sf blueprint0.jpg ``` and we can get the flag
