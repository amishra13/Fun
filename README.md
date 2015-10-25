import java.awt.Color;
import java.awt.Graphics;
import java.awt.Rectangle;
import javax.swing.JFrame;
import java.awt.event.KeyAdapter;
import java.awt.event.KeyEvent;


public class Fun extends JFrame
{

	public boolean right = false;
	public boolean left = false;
	public boolean up = false;
	public boolean down = false;
	public boolean right1 = false;
	public boolean left1 = false;
	public boolean up1 = false;
	public boolean down1 = false;
	Rectangle character = new Rectangle(200,300, 24, 36 );
	Rectangle player = new Rectangle(1100,300,24,36);
	Rectangle monster1 = new Rectangle(0,0,10,10);
	Rectangle monster2 = new Rectangle(1200,0,10,10);
	Rectangle monster3 = new Rectangle(0,700,10,10);
	Rectangle monster4 = new Rectangle(1200,700,10,10);
	Rectangle chomper1 = new Rectangle(590,165,10,10);
	Rectangle chomper2 = new Rectangle(590,515,10,10);
	Rectangle chomper3 = new Rectangle(290,340,10,10);
	Rectangle chomper4 = new Rectangle(890,340,10,10);
	Rectangle control = new Rectangle (575,325,50,50);
	Rectangle control1= new Rectangle (50,75,50,50);
	Rectangle control2 = new Rectangle (1100,75,50,50);
	Rectangle control3 = new Rectangle (50,600,50,50);
	Rectangle control4 = new Rectangle (1100,600,50,50);
	
	int q = 1;
	int r = 1;
	int s = 1;
	int t = 1;
	int kill1 = 0;
	int kill2 = 0;
	
	public int u = 0;
	public int round = 2;
	
	public int redpoints = 0;
	public int whitepoints = 0;
	
	
	
	public Fun()
	{
		
		
		this.addKeyListener(new KeyAdapter()
		{
			
			public void keyPressed(KeyEvent e)
			{
				if(e.getKeyCode() == KeyEvent.VK_D)
				{
					
					right = true;
				}
				
				if(e.getKeyCode() == KeyEvent.VK_L)
				{
					
					right1 = true;
					
				}
				if(e.getKeyCode() == KeyEvent.VK_A)
				{
					
					left = true;
					
				}
				
				if(e.getKeyCode() == KeyEvent.VK_J)
				{
					
					left1 = true;
					
				}
				
				if(e.getKeyCode() == KeyEvent.VK_W)
				{
					
					
					up = true;
					
				}
				
				if(e.getKeyCode() == KeyEvent.VK_I)
				{
					
					up1 = true;
					
				}
				if(e.getKeyCode() == KeyEvent.VK_S)
				{
					
					
					down = true;
					
				}
				if(e.getKeyCode() == KeyEvent.VK_K)
				{
					
					down1 = true;
					
				}
				
			}
			
			public void keyReleased(KeyEvent e)
			{
				
				if(e.getKeyCode() == KeyEvent.VK_D)
				{
					
					right = false;
				}
				if(e.getKeyCode() == KeyEvent.VK_L)
				{
					
					right1 = false;
					
				}
				if(e.getKeyCode() == KeyEvent.VK_A)
				{
					
					left = false;
				}
				if(e.getKeyCode() == KeyEvent.VK_J)
				{
					
					left1 = false;
					
				}
				
				
				if(e.getKeyCode() == KeyEvent.VK_W)
				{
					
				
					up = false;
					
				}
				
				if(e.getKeyCode() == KeyEvent.VK_I)
				{
					
					up1 = false;
					
				}
				if(e.getKeyCode() == KeyEvent.VK_S)
				{
					
					
					down = false;
					
				}
				if(e.getKeyCode() == KeyEvent.VK_K)
				{
					
					down1 = false;
				}
				
			}
			
	});

		
	}
	
	public void paint (Graphics g)
	{
		
		super.paint(g);
		g.drawLine(600,0,600,700);
		g.drawLine(0,350,1200,350);
		
		this.setBackground(Color.BLUE);
		g.setColor(Color.WHITE);
		g.fillRect(character.x, character.y, character.width, character.height );
		g.setColor(Color.RED);
		g.fillRect(player.x,player.y,player.width,player.height);
		
		
		g.setColor(Color.BLACK);
		g.fillRect(monster1.x, monster1.y, monster1.width, monster1.height);
		g.fillRect(monster2.x, monster2.y, monster2.width, monster2.height);
		g.fillRect(monster3.x, monster3.y, monster3.width, monster3.height);
		g.fillRect(monster4.x, monster4.y, monster4.width, monster4.height);
		g.fillRect(chomper1.x, chomper1.y, chomper1.width, chomper1.height);
		g.fillRect(chomper2.x, chomper2.y, chomper2.width, chomper2.height);
		g.fillRect(chomper3.x, chomper3.y, chomper3.width, chomper3.height);
		g.fillRect(chomper4.x, chomper4.y, chomper4.width, chomper4.height);
	
		g.setColor(Color.YELLOW);
		g.fillRect(control.x, control.y, control.width, control.height);
		g.fillRect(control1.x, control1.y, control1.width, control1.height);
		g.fillRect(control2.x, control2.y, control2.width, control2.height);
		g.fillRect(control3.x, control3.y, control3.width, control3.height);
		g.fillRect(control4.x, control4.y, control4.width, control4.height);
	
		
		
		if (right)
		{
			
			character.x += 10;
			
			
		}
		
		if(right1)
		{
			
			player.x += 10;
		
		}
		if(left)
		{
			
			character.x -= 10;
			
		}
		if(left1)
		{
			
			player.x -= 10;
		}
		if(up)
		{
			
			character.y -= 10;
		
		}
		if(up1)
		{
		    player.y -= 10;
			
		}
		if(down)
		{
			
			
			character.y += 10;
		}
		if(down1)
		{
			
			player.y += 10;
			
		}
		
		if (character.x == 0)
		{
			left = false;
			character.x += 10;
			
		}
		
		if(character.x == 1150)
		{
			
			right = false;
			character.x -= 10;
			
		}
		
		if(character.y == 0)
		{
			
			up = false;
			character.y += 10;
			
		}
		
		if(character.y == 650)
		{
			
			down = false;
			character.y -= 10;
		}
		
		if (player.x == 0)
		{
			left1 = false;
			player.x += 10;
			
		}
		
		if(player.x == 1150)
		{
			
			right1 = false;
			player.x -= 10;
			
		}
		
		if(player.y == 0)
		{
			
			up1 = false;
			player.y += 10;
			
		}
		
		if(player.y == 650)
		{
			
			down1 = false;
			player.y -= 10;
		}
		
		
		
		
		for(int a = 0; a<24; a++)
		{
			
			if (character.x == player.x + a )
			{
				for (int b = 0; b< 36; b++)
				{
				  if(character.y == player.y + b)
				  {
					
				
					player.setLocation(-90000,-90000);
					
					
				  }
				}
				
				
			}
			
			
			
		}
		
		
		
		
		
		for(int a = 0; a<24; a++)
		{
			
			if (player.x == character.x + a )
			{
				for (int b = 0; b< 36; b++)
				{
				  if(player.y == character.y + b)
				  {
					
					  
						character.setLocation(-90000,-90000);
						
					
					
				  }
				}
				
				
			}
			
			
			
		}
		
		
		
		
		
		// KILLER FUNCTIONS!!!!
		
		for(int a = 0; a<24; a++)
		{
			
			if (monster1.x == character.x + a )
			{
				for (int b = 0; b< 36; b++)
				{
				  if(monster1.y == character.y + b)
				  {
					
					character.setLocation(-90000,-90000);
					
					
				  }
				}
				
				
			}
			
			
			
		}
		
		for(int a = 0; a<24; a++)
		{
			
			if (monster1.x == player.x + a )
			{
				for (int b = 0; b< 36; b++)
				{
				  if(monster1.y == player.y + b)
				  {
					
					player.setLocation(-90000,-90000);
					
					
				  }
				}
				
				
			}
			
			
			
		}
		
		for(int a = 0; a<24; a++)
		{
			
			if (monster2.x == character.x + a )
			{
				for (int b = 0; b< 36; b++)
				{
				  if(monster2.y == character.y + b)
				  {
					
					character.setLocation(-90000,-90000);
					
					
				  }
				}
				
				
			}
			
			
			
		}
		
		for(int a = 0; a<24; a++)
		{
			
			if (monster3.x == character.x + a )
			{
				for (int b = 0; b< 36; b++)
				{
				  if(monster3.y == character.y + b)
				  {
					
					character.setLocation(-90000,-90000);
					
					
				  }
				}
				
				
			}
			
			
			
		}
		
		for(int a = 0; a<24; a++)
		{
			
			if (monster4.x == character.x + a )
			{
				for (int b = 0; b< 36; b++)
				{
				  if(monster4.y == character.y + b)
				  {
					
					character.setLocation(-90000,-90000);
					
					
				  }
				}
				
				
			}
			
			
			
		}
		
		for(int a = 0; a<24; a++)
		{
			
			if (monster2.x == player.x + a )
			{
				for (int b = 0; b< 36; b++)
				{
				  if(monster2.y == player.y + b)
				  {
					
					player.setLocation(-90000,-90000);
					
					
				  }
				}
				
				
			}
			
			
			
		}
		
		for(int a = 0; a<24; a++)
		{
			
			if (monster3.x == player.x + a )
			{
				for (int b = 0; b< 36; b++)
				{
				  if(monster3.y == player.y + b)
				  {
					
					player.setLocation(-90000,-90000);
					
					
				  }
				}
				
				
			}
			
			
			
		}
		
		for(int a = 0; a<24; a++)
		{
			
			if (monster4.x == player.x + a )
			{
				for (int b = 0; b< 36; b++)
				{
				  if(monster4.y == player.y + b)
				  {
					
					player.setLocation(-90000,-90000);
					
					
				  }
				}
				
				
			}
			
			
			
		}
		
		
		for(int a = 0; a<24; a++)
		{
			
			if (chomper1.x == player.x + a )
			{
				for (int b = 0; b< 36; b++)
				{
				  if(chomper1.y == player.y + b)
				  {
					
					player.setLocation(-90000,-90000);
					
					
				  }
				}
				
				
			}
			
			
			
		}
		
		for(int a = 0; a<24; a++)
		{
			
			if (chomper2.x == player.x + a )
			{
				for (int b = 0; b< 36; b++)
				{
				  if(chomper2.y == player.y + b)
				  {
					
					player.setLocation(-90000,-90000);
					
					
				  }
				}
				
				
			}
			
			
			
		}
		
		for(int a = 0; a<24; a++)
		{
			
			if (chomper3.x == player.x + a )
			{
				for (int b = 0; b< 36; b++)
				{
				  if(chomper3.y == player.y + b)
				  {
					
					player.setLocation(-90000,-90000);
					
					
				  }
				}
				
				
			}
			
			
			
		}
		
		
		for(int a = 0; a<24; a++)
		{
			
			if (chomper4.x == player.x + a )
			{
				for (int b = 0; b< 36; b++)
				{
				  if(chomper4.y == player.y + b)
				  {
					
					player.setLocation(-90000,-90000);
					
					
				  }
				}
				
				
			}
			
			
			
		}
		
		
		for(int a = 0; a<24; a++)
		{
			
			if (chomper1.x == character.x + a )
			{
				for (int b = 0; b< 36; b++)
				{
				  if(chomper1.y == character.y + b)
				  {
					
					character.setLocation(-90000,-90000);
					
					
				  }
				}
				
				
			}
			
			
			
		}
		
		for(int a = 0; a<24; a++)
		{
			
			if (chomper2.x == character.x + a )
			{
				for (int b = 0; b< 36; b++)
				{
				  if(chomper2.y == character.y + b)
				  {
					
					character.setLocation(-90000,-90000);
					
					
				  }
				}
				
				
			}
			
			
			
		}
		
		for(int a = 0; a<24; a++)
		{
			
			if (chomper3.x == character.x + a )
			{
				for (int b = 0; b< 36; b++)
				{
				  if(chomper3.y == character.y + b)
				  {
					
					character.setLocation(-90000,-90000);
					
					
				  }
				}
				
				
			}
			
			
			
		}
		
		
		for(int a = 0; a<24; a++)
		{
			
			if (chomper4.x == character.x + a )
			{
				for (int b = 0; b< 36; b++)
				{
					
				  if(chomper4.y == character.y + b)
				  {
					
					character.setLocation(-90000,-90000);
					
					
				  }
				}
				
				
			}
			
			
			
		}
		
		for(int a = 0; a<600; a++)
		{
			
			if (character.x == a )
			{
				for (int b = 0; b< 350; b++)
				{
				  if(character.y == b)
				  {
					
					q = 2;
					break;
					
				  }
				}
				
				break;
			}
			
			q = 1;
			
		}
		
		for(int a = 600; a<1200; a++)
		{
			
			if (character.x == a )
			{
				for (int b = 0; b< 350; b++)
				{
				  if(character.y == b)
				  {
					
					r = 2;
					break;
					
				  }
				}
				
				break;
			}
			
			r = 1;
			
		}
		
		
		
		for(int a = 0; a<600; a++)
		{
			
			if (character.x == a )
			{
				for (int b = 350; b< 700; b++)
				{
				  if(character.y == b)
				  {
					
					s = 2;
					
					break;
				  }
				}
				
				break;
			}
			
			s = 1;
			
		}
		
		
		
		for(int a = 600; a<1200; a++)
		{
			
			if (character.x == a )
			{
				for (int b = 350; b< 700; b++)
				{
				  if(character.y == b)
				  {
					
					t = 2;
					break;
					
				  }
				}
				
				break;
			}
			
			t = 1;
			
		}
		
		
				
				for(int a = 0; a<600; a++)
				{
					
					if (player.x == a )
					{
						for (int b = 0; b< 350; b++)
						{
						  if(player.y == b)
						  {
							
							q = 2;
							break;
							
						  }
						}
						
						break;
					}
					
					q = 1;
					
				}
				
				for(int a = 600; a<1200; a++)
				{
					
					if (player.x == a )
					{
						for (int b = 0; b< 350; b++)
						{
						  if(player.y == b)
						  {
							
							r = 2;
							break;
							
						  }
						}
						
						break;
					}
					
					r = 1;
					
				}
				
				
				
				for(int a = 0; a<600; a++)
				{
					
					if (player.x == a )
					{
						for (int b = 350; b< 700; b++)
						{
						  if(player.y == b)
						  {
							
							s = 2;
							
							break;
						  }
						}
						
						break;
					}
					
					s = 1;
					
				}
				
				
				
				for(int a = 600; a<1200; a++)
				{
					
					if (player.x == a )
					{
						for (int b = 350; b< 700; b++)
						{
						  if(player.y == b)
						  {
							
							t = 2;
							break;
							
						  }
						}
						
						break;
					}
					
					t = 1;
					
				}
				
				
				for (int a = 575; a< 625; a++)
				{
					
					if (player.x == a )
					{
						for (int b = 325; b< 375; b++)
						{
						  if(player.y == b)
						  {
							
							chomper1.setLocation(500,50);
							chomper2.setLocation(300,250);
							chomper3.setLocation(850,250);
							chomper4.setLocation(500,550);
							
							break;
						  }
						}
						
						break;
					}
					
					
				}
				
				
				for (int a = 575; a< 625; a++)
				{
					
					if (character.x == a )
					{
						for (int b = 325; b< 375; b++)
						{
						  if(character.y == b)
						  {
							
							chomper1.setLocation(500,50);
							chomper2.setLocation(300,250);
							chomper3.setLocation(850,250);
							chomper4.setLocation(500,550);
							
							break;
						  }
						}
						
						break;
					}
					
					
				}
				
				
				for (int a = 50; a< 100; a++)
				{
					
					if (character.x == a )
					{
						for (int b = 75; b< 175; b++)
						{
						  if(character.y == b)
						  {
							
							chomper1.setLocation(player.x - 50, player.y - 50);
							character.setLocation(520,270);
							
							break;
						  }
						}
						
						break;
					}
					
					
				}
				
				for (int a = 1100; a< 1150; a++)
				{
					
					if (character.x == a )
					{
						for (int b = 75; b< 125; b++)
						{
						  if(character.y == b)
						  {
							
							  chomper2.setLocation(player.x - 50, player.y - 50);
							  character.setLocation(520,270);
							
							break;
						  }
						}
						
						break;
					}
					
					
				}
				
				for (int a = 50; a< 100; a++)
				{
					
					if (character.x == a )
					{
						for (int b = 600; b< 650; b++)
						{
						  if(character.y == b)
						  {
							
							  chomper3.setLocation(player.x - 50, player.y - 50);
							  character.setLocation(520,270);
							
							break;
						  }
						}
						
						break;
					}
					
					
				}
				
				
				for (int a = 1100; a< 1150; a++)
				{
					
					if (character.x == a )
					{
						for (int b = 600; b< 650; b++)
						{
						  if(character.y == b)
						  {
							
							  chomper4.setLocation(player.x - 50, player.y - 50);
							  character.setLocation(520,270);
							
							break;
						  }
						}
						
						break;
					}
					
					
				}
				
				
				for (int a = 50; a< 100; a++)
				{
					
					if (player.x == a )
					{
						for (int b = 75; b< 175; b++)
						{
						  if(player.y == b)
						  {
							
							  chomper1.setLocation(character.x - 50, character.y - 50);
							  player.setLocation(520,270);
							
							break;
						  }
						}
						
						break;
					}
					
					
				}
				
				for (int a = 1100; a< 1150; a++)
				{
					
					if (player.x == a )
					{
						for (int b = 75; b< 125; b++)
						{
						  if(player.y == b)
						  {
							
							  chomper2.setLocation(character.x - 50, character.y - 50);
							  player.setLocation(520,270);
							break;
						  }
						}
						
						break;
					}
					
					
				}
				
				for (int a = 50; a< 100; a++)
				{
					
					if (player.x == a )
					{
						for (int b = 600; b< 650; b++)
						{
						  if(player.y == b)
						  {
							
							  chomper3.setLocation(character.x - 50, character.y - 50);
							  player.setLocation(520,270);
							
							break;
						  }
						}
						
						break;
					}
					
					
				}
				
				
				for (int a = 1100; a< 1150; a++)
				{
					
					if (player.x == a )
					{
						for (int b = 600; b< 650; b++)
						{
						  if(player.y == b)
						  {
							
							  chomper4.setLocation(character.x - 50, character.y - 50);
							  player.setLocation(520,270);
							
							break;
						  }
						}
						
						break;
					}
					
					
				}
		
		
		////////////////////////////////
		
		while (u< 40)
		{
			
			monster1.x += 20;
			
			u++;
			break;
			
		}
		
		while (u >= 40 && u < 80)
		{
			
			monster1.y += 20;
			
			u++;
			break;
			
		}
		
		while (u >= 80 && u < 120)
		{
			
			monster1.x -= 20;
			
			u++;
			break;
			
		}
		
		while(u >= 120 && u < 160)
		{
			
			monster1. y -= 20;
			
			u++;
			break;
			
		}
		if (u == 160)
		{
			
			u = 0;
			
		}
		//////////////
		
		while (u< 40)
		{
			
			
			monster2.y += 20;
			
			u++;
			break;
			
		}
		
		while (u >= 40 && u < 80)
		{
			
			
			monster2.x -= 20;
			
			u++;
			break;
			
		}
		
		while (u >= 80 && u < 120)
		{
			
			
			monster2.y -= 20;
			
			u++;
			break;
			
		}
		
		while(u >= 120 && u < 160)
		{
			
			
			monster2. x += 20;
			
			u++;
			break;
			
		}
		/////////////
		
		while (u< 40)
		{
			
			
			monster3.y -= 20;
			
			u++;
			break;
			
		}
		
		while (u >= 40 && u < 80)
		{
			
			
			monster3.x += 20;
			
			u++;
			break;
			
		}
		
		while (u >= 80 && u < 120)
		{
			
			
			monster3.y += 20;
			
			u++;
			break;
			
		}
		
		while(u >= 120 && u < 160)
		{
			
			
			monster3.x -= 20;
			
			u++;
			break;
			
		}
		//////////////
		
		while (u< 40)
		{
			
			
			monster4.x -= 20;
			u++;
			break;
			
		}
		
		while (u >= 40 && u < 80)
		{
			
			
			monster4.y -= 20;
			u++;
			break;
			
		}
		
		while (u >= 80 && u < 120)
		{
			
		
			monster4.x += 20;
			u++;
			break;
			
		}
		
		while(u >= 120 && u < 160)
		{
			
			
			monster4. y += 20;
			u++;
			break;
			
		}
		////////////
		
		
		
		while (u< 40)
		{
			
			chomper1.x += 10 * q;
			chomper2.x += 10 * q;
			chomper3.x += 10 * q;
			chomper4.x += 10 * q;
			u++;
			break;
			
		}
		
		while (u >= 40 && u < 80)
		{
			
			chomper1.y += 10 * r;
			chomper2.y += 10 * r;
			chomper3.y += 10 * r;
			chomper4.y += 10 * r;
			u++;
			break;
			
		}
		
		while (u >= 80 && u < 120)
		{
			
			chomper1.x -= 10 * s;
			chomper2.x -= 10 * s;
			chomper3.x -= 10 * s;
			chomper4.x -= 10 * s;
			u++;
			break;
			
		}
		
		while(u >= 120 && u < 160)
		{
			
			chomper1. y -= 10 * t;
			chomper2. y -= 10 * t;
			chomper3. y -= 10 * t;
			chomper4. y -= 10 * t;
			u++;
			break;
			
		}
		if (u == 160)
		{
			
			u = 0;
			
		}
		
		/////////////////
		
		if (player.x < 0 && player.y < 0 && character.x > 0 && character.y >0)
		{
			
			
			g.drawString("WHITE WON!! begin round " + round ,550, 200);
			round++;
			whitepoints++;
			
			if(character.x < 200)
			{
			player.setLocation(1100,300);
			}	
			
			else
			{
				
				round--;
				whitepoints--;
				
			}
			
			
		}
		
		if (character.x < 0 && character.y < 0  && player.x > 0 && player.y > 0)
		{
			
			
			g.drawString("RED WON!!  begin round " + round,550, 200);
			round++;
			redpoints++;
			if(player.x >1100)
			{
			character.setLocation(200,300);
			
			}
			else
			{
				
				round--;
				redpoints--;
			}
		}
		
		if(character.x < 0 && character.y < 0  && player.x < 0 && player.y < 0)
		{
			if(redpoints > whitepoints)
			{
			g.drawString("GAME OVER! RED HAS SECURED MORE VICTORIES!", 475, 200);
			}
			
			if(whitepoints > redpoints)
			{
				
				g.drawString("GAME OVER! WHITE HAS SECURED MORE VICTORIES!", 475, 200);
				
			}
			
			if(whitepoints == redpoints)
			{
				
				g.drawString("GAME OVER! RED and WHITE HAVE SECURED EQUAL VICTORIES!", 400, 200);
			}
			
		}
		
		repaint();
		
		
	}
	
	
	public static void main(String[] args)
	{
		Fun window = new Fun();
		window.setSize(1200,700);
		window.setResizable(true);
		window.setVisible(true);
		window.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
		window.setTitle("Red VS. White");
		window.setLocationRelativeTo(null);
		
		
		
	}
	
	
	
	
}
