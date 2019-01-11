using System;
using System.Drawing;
using System.Drawing.Drawing2D;		// for GraphicsPath
using System.Collections;
using System.ComponentModel;
using System.Windows.Forms;
using TSOP.Games.IconMemoryGame;
using System.Threading;
using System.Diagnostics;
using TSOP.Multimedia;

namespace TSOP.Games.IconMemoryGame
{
	/// <summary>
	/// Summary description for MemoryForm.
	/// </summary>
	public class MemoryForm : System.Windows.Forms.Form, IGameBoardDisplay
	{
		#region Constructors, Declarations and Initializations

		private System.Windows.Forms.MainMenu mainMenu1;
		private System.Windows.Forms.MenuItem menuItem1;
		private System.Windows.Forms.GroupBox scoreGroup;
		private System.Windows.Forms.TextBox score1Text;
		private System.Windows.Forms.Label player1Label;
		private Graphics graphicsObject;
		private System.ComponentModel.IContainer components;
		private System.Windows.Forms.MenuItem menuItem2;
		private System.Windows.Forms.StatusBar statusBar;
		private System.Windows.Forms.StatusBarPanel statusBarText;
		private System.Windows.Forms.StatusBarPanel statusBarCount;
		private System.Windows.Forms.MenuItem menuNew1P;
		private System.Windows.Forms.MenuItem menuNew1PvC;
		private System.Windows.Forms.MenuItem menuNew2P;
		private System.Windows.Forms.TextBox score2Text;
		private System.Windows.Forms.Label player2Label;

		private MemoryGame theGame;

		/// <summary>
		/// Field to instantiate the status monitor thread
		/// </summary>
		private StatusMonitor statMon;
		private System.Windows.Forms.MenuItem menuFileExit;
		
//		private Thread statusThread;
		private System.Windows.Forms.MenuItem menuItem4;
		private System.Windows.Forms.MenuItem menuOptions;
		private System.Windows.Forms.MenuItem menuOptionsDifficulty;
		private System.Windows.Forms.MenuItem menuOptionsDifficulty0;
		private System.Windows.Forms.MenuItem menuOptionsDifficulty1;
		private System.Windows.Forms.MenuItem menuOptionsDifficulty2;
		private System.Windows.Forms.MenuItem menuOptionsDifficulty3;
		private System.Windows.Forms.MenuItem menuOptionsDifficulty4;
		private System.Windows.Forms.MenuItem menuOptionsDifficulty5;
		private System.Windows.Forms.Timer statusTimer;
		private System.Windows.Forms.Timer moveTimer;

		/// <summary>
		/// Field to record last card selected
		/// </summary>
		private Position rowColumn;

		/// <summary>
		/// count to make sure at least 10 .1sec intervals have occurred since last timer action
		/// </summary>
		private int m_moveTimerCount;

		/// <summary>
		/// time to delay between actions (in 1/10's of a second)
		/// </summary>
		private int m_delayTime = 8;

		/// <summary>
		/// remembers the control flags passed by the status monitor
		/// </summary>
		private int lastControlFlags = 0;
		private System.Windows.Forms.MenuItem menuOptionsSpeed;
		private System.Windows.Forms.MenuItem menuOptionsSpeedSlow;
		private System.Windows.Forms.MenuItem menuOptionsSpeedRegular;
		private System.Windows.Forms.MenuItem menuOptionsSpeedFast;
		private System.Windows.Forms.Button cheatButton;
		private System.Windows.Forms.MenuItem menuHelp;
		private System.Windows.Forms.HelpProvider helper;
		private System.Windows.Forms.MenuItem menuHelpTopics;
		private System.Windows.Forms.MenuItem menuHelpAbout;
		private System.Windows.Forms.MenuItem menuItem6;
		private System.Windows.Forms.MenuItem menuFileHighScores;
		private System.Windows.Forms.Button buttonTest;

		/// <summary>
		/// the region in which the game board is displayed
		/// </summary>
		public Rectangle m_gameBoardRect = new Rectangle(152,16,344,344);
		
		/// <summary>
		/// Default Constructor
		/// </summary>
		public MemoryForm()
		{
			//
			// Required for Windows Form Designer support
			//

			InitializeComponent();

			graphicsObject = this.CreateGraphics();
			
			theGame = new MemoryGame(this);

			statMon = new StatusMonitor(this, theGame);
			
			m_moveTimerCount = 0;
		}
		#endregion

		#region Windows Form Designer generated code
		/// <summary>
		/// Required method for Designer support - do not modify
		/// the contents of this method with the code editor.
		/// </summary>
		private void InitializeComponent()
		{
			this.components = new System.ComponentModel.Container();
			System.Resources.ResourceManager resources = new System.Resources.ResourceManager(typeof(MemoryForm));
			this.mainMenu1 = new System.Windows.Forms.MainMenu();
			this.menuItem1 = new System.Windows.Forms.MenuItem();
			this.menuItem2 = new System.Windows.Forms.MenuItem();
			this.menuNew1P = new System.Windows.Forms.MenuItem();
			this.menuNew1PvC = new System.Windows.Forms.MenuItem();
			this.menuNew2P = new System.Windows.Forms.MenuItem();
			this.menuFileHighScores = new System.Windows.Forms.MenuItem();
			this.menuFileExit = new System.Windows.Forms.MenuItem();
			this.menuOptions = new System.Windows.Forms.MenuItem();
			this.menuOptionsDifficulty = new System.Windows.Forms.MenuItem();
			this.menuOptionsDifficulty0 = new System.Windows.Forms.MenuItem();
			this.menuOptionsDifficulty1 = new System.Windows.Forms.MenuItem();
			this.menuOptionsDifficulty2 = new System.Windows.Forms.MenuItem();
			this.menuOptionsDifficulty3 = new System.Windows.Forms.MenuItem();
			this.menuOptionsDifficulty4 = new System.Windows.Forms.MenuItem();
			this.menuOptionsDifficulty5 = new System.Windows.Forms.MenuItem();
			this.menuOptionsSpeed = new System.Windows.Forms.MenuItem();
			this.menuOptionsSpeedSlow = new System.Windows.Forms.MenuItem();
			this.menuOptionsSpeedRegular = new System.Windows.Forms.MenuItem();
			this.menuOptionsSpeedFast = new System.Windows.Forms.MenuItem();
			this.menuHelp = new System.Windows.Forms.MenuItem();
			this.menuHelpTopics = new System.Windows.Forms.MenuItem();
			this.menuItem6 = new System.Windows.Forms.MenuItem();
			this.menuHelpAbout = new System.Windows.Forms.MenuItem();
			this.scoreGroup = new System.Windows.Forms.GroupBox();
			this.score2Text = new System.Windows.Forms.TextBox();
			this.player2Label = new System.Windows.Forms.Label();
			this.score1Text = new System.Windows.Forms.TextBox();
			this.player1Label = new System.Windows.Forms.Label();
			this.statusBar = new System.Windows.Forms.StatusBar();
			this.statusBarText = new System.Windows.Forms.StatusBarPanel();
			this.statusBarCount = new System.Windows.Forms.StatusBarPanel();
			this.cheatButton = new System.Windows.Forms.Button();
			this.menuItem4 = new System.Windows.Forms.MenuItem();
			this.statusTimer = new System.Windows.Forms.Timer(this.components);
			this.moveTimer = new System.Windows.Forms.Timer(this.components);
			this.helper = new System.Windows.Forms.HelpProvider();
			this.buttonTest = new System.Windows.Forms.Button();
			this.scoreGroup.SuspendLayout();
			((System.ComponentModel.ISupportInitialize)(this.statusBarText)).BeginInit();
			((System.ComponentModel.ISupportInitialize)(this.statusBarCount)).BeginInit();
			this.SuspendLayout();
			// 
			// mainMenu1
			// 
			this.mainMenu1.MenuItems.AddRange(new System.Windows.Forms.MenuItem[] {
																					  this.menuItem1,
																					  this.menuOptions,
																					  this.menuHelp});
			// 
			// menuItem1
			// 
			this.menuItem1.DefaultItem = true;
			this.menuItem1.Index = 0;
			this.menuItem1.MenuItems.AddRange(new System.Windows.Forms.MenuItem[] {
																					  this.menuItem2,
																					  this.menuFileHighScores,
																					  this.menuFileExit});
			this.menuItem1.Text = "&File";
			// 
			// menuItem2
			// 
			this.menuItem2.Index = 0;
			this.menuItem2.MenuItems.AddRange(new System.Windows.Forms.MenuItem[] {
																					  this.menuNew1P,
																					  this.menuNew1PvC,
																					  this.menuNew2P});
			this.menuItem2.Text = "New";
			// 
			// menuNew1P
			// 
			this.menuNew1P.Index = 0;
			this.menuNew1P.Text = "1 Player";
			this.menuNew1P.Click += new System.EventHandler(this.menuNew1P_Click);
			// 
			// menuNew1PvC
			// 
			this.menuNew1PvC.Index = 1;
			this.menuNew1PvC.Text = "1 Player vs. Computer";
			this.menuNew1PvC.Click += new System.EventHandler(this.menuNew1PvC_Click);
			// 
			// menuNew2P
			// 
			this.menuNew2P.Index = 2;
			this.menuNew2P.Text = "2 Players";
			this.menuNew2P.Click += new System.EventHandler(this.menuNew2P_Click);
			// 
			// menuFileHighScores
			// 
			this.menuFileHighScores.Index = 1;
			this.menuFileHighScores.Text = "High Scores...";
			this.menuFileHighScores.Click += new System.EventHandler(this.menuFileHighScores_Click);
			// 
			// menuFileExit
			// 
			this.menuFileExit.Index = 2;
			this.menuFileExit.Text = "&Exit";
			this.menuFileExit.Click += new System.EventHandler(this.menuFileExit_Click);
			// 
			// menuOptions
			// 
			this.menuOptions.Index = 1;
			this.menuOptions.MenuItems.AddRange(new System.Windows.Forms.MenuItem[] {
																						this.menuOptionsDifficulty,
																						this.menuOptionsSpeed});
			this.menuOptions.Text = "&Options";
			// 
			// menuOptionsDifficulty
			// 
			this.menuOptionsDifficulty.Index = 0;
			this.menuOptionsDifficulty.MenuItems.AddRange(new System.Windows.Forms.MenuItem[] {
																								  this.menuOptionsDifficulty0,
																								  this.menuOptionsDifficulty1,
																								  this.menuOptionsDifficulty2,
																								  this.menuOptionsDifficulty3,
																								  this.menuOptionsDifficulty4,
																								  this.menuOptionsDifficulty5});
			this.menuOptionsDifficulty.Text = "Difficulty";
			// 
			// menuOptionsDifficulty0
			// 
			this.menuOptionsDifficulty0.Enabled = false;
			this.menuOptionsDifficulty0.Index = 0;
			this.menuOptionsDifficulty0.Text = "0 (Easy)";
			this.menuOptionsDifficulty0.Click += new System.EventHandler(this.menuOptionsDifficultyX_Click);
			// 
			// menuOptionsDifficulty1
			// 
			this.menuOptionsDifficulty1.Enabled = false;
			this.menuOptionsDifficulty1.Index = 1;
			this.menuOptionsDifficulty1.Text = "1";
			this.menuOptionsDifficulty1.Click += new System.EventHandler(this.menuOptionsDifficultyX_Click);
			// 
			// menuOptionsDifficulty2
			// 
			this.menuOptionsDifficulty2.Enabled = false;
			this.menuOptionsDifficulty2.Index = 2;
			this.menuOptionsDifficulty2.Text = "2";
			this.menuOptionsDifficulty2.Click += new System.EventHandler(this.menuOptionsDifficultyX_Click);
			// 
			// menuOptionsDifficulty3
			// 
			this.menuOptionsDifficulty3.Checked = true;
			this.menuOptionsDifficulty3.Enabled = false;
			this.menuOptionsDifficulty3.Index = 3;
			this.menuOptionsDifficulty3.Text = "3";
			this.menuOptionsDifficulty3.Click += new System.EventHandler(this.menuOptionsDifficultyX_Click);
			// 
			// menuOptionsDifficulty4
			// 
			this.menuOptionsDifficulty4.Enabled = false;
			this.menuOptionsDifficulty4.Index = 4;
			this.menuOptionsDifficulty4.Text = "4";
			this.menuOptionsDifficulty4.Click += new System.EventHandler(this.menuOptionsDifficultyX_Click);
			// 
			// menuOptionsDifficulty5
			// 
			this.menuOptionsDifficulty5.Enabled = false;
			this.menuOptionsDifficulty5.Index = 5;
			this.menuOptionsDifficulty5.Text = "5 (Impossible)";
			this.menuOptionsDifficulty5.Click += new System.EventHandler(this.menuOptionsDifficultyX_Click);
			// 
			// menuOptionsSpeed
			// 
			this.menuOptionsSpeed.Index = 1;
			this.menuOptionsSpeed.MenuItems.AddRange(new System.Windows.Forms.MenuItem[] {
																							 this.menuOptionsSpeedSlow,
																							 this.menuOptionsSpeedRegular,
																							 this.menuOptionsSpeedFast});
			this.menuOptionsSpeed.Text = "Game Speed";
			// 
			// menuOptionsSpeedSlow
			// 
			this.menuOptionsSpeedSlow.Index = 0;
			this.menuOptionsSpeedSlow.Text = "Slow";
			this.menuOptionsSpeedSlow.Click += new System.EventHandler(this.menuOptionsSpeed_Click);
			// 
			// menuOptionsSpeedRegular
			// 
			this.menuOptionsSpeedRegular.Checked = true;
			this.menuOptionsSpeedRegular.Index = 1;
			this.menuOptionsSpeedRegular.Text = "Normal";
			this.menuOptionsSpeedRegular.Click += new System.EventHandler(this.menuOptionsSpeed_Click);
			// 
			// menuOptionsSpeedFast
			// 
			this.menuOptionsSpeedFast.Index = 2;
			this.menuOptionsSpeedFast.Text = "Fast";
			this.menuOptionsSpeedFast.Click += new System.EventHandler(this.menuOptionsSpeed_Click);
			// 
			// menuHelp
			// 
			this.menuHelp.Index = 2;
			this.menuHelp.MenuItems.AddRange(new System.Windows.Forms.MenuItem[] {
																					 this.menuHelpTopics,
																					 this.menuItem6,
																					 this.menuHelpAbout});
			this.menuHelp.Text = "Help";
			// 
			// menuHelpTopics
			// 
			this.menuHelpTopics.Index = 0;
			this.menuHelpTopics.Text = "Help Topics";
			this.menuHelpTopics.Click += new System.EventHandler(this.menuHelp_Click);
			// 
			// menuItem6
			// 
			this.menuItem6.Index = 1;
			this.menuItem6.Text = "-";
			// 
			// menuHelpAbout
			// 
			this.menuHelpAbout.Index = 2;
			this.menuHelpAbout.Text = "About...";
			this.menuHelpAbout.Click += new System.EventHandler(this.menuHelp_Click);
			// 
			// scoreGroup
			// 
			this.scoreGroup.BackColor = System.Drawing.Color.CornflowerBlue;
			this.scoreGroup.Controls.AddRange(new System.Windows.Forms.Control[] {
																					 this.score2Text,
																					 this.player2Label,
																					 this.score1Text,
																					 this.player1Label});
			this.scoreGroup.ForeColor = System.Drawing.Color.FromArgb(((System.Byte)(255)), ((System.Byte)(255)), ((System.Byte)(200)));
			this.scoreGroup.Location = new System.Drawing.Point(8, 8);
			this.scoreGroup.Name = "scoreGroup";
			this.scoreGroup.Size = new System.Drawing.Size(128, 96);
			this.scoreGroup.TabIndex = 0;
			this.scoreGroup.TabStop = false;
			this.scoreGroup.Text = "Score";
			// 
			// score2Text
			// 
			this.score2Text.BackColor = System.Drawing.Color.FromArgb(((System.Byte)(255)), ((System.Byte)(255)), ((System.Byte)(200)));
			this.score2Text.Font = new System.Drawing.Font("Comic Sans MS", 9.75F, System.Drawing.FontStyle.Bold, System.Drawing.GraphicsUnit.Point, ((System.Byte)(0)));
			this.score2Text.ForeColor = System.Drawing.Color.Black;
			this.score2Text.Location = new System.Drawing.Point(80, 64);
			this.score2Text.Name = "score2Text";
			this.score2Text.ReadOnly = true;
			this.score2Text.Size = new System.Drawing.Size(40, 26);
			this.score2Text.TabIndex = 2;
			this.score2Text.Text = "0";
			this.score2Text.TextAlign = System.Windows.Forms.HorizontalAlignment.Center;
			// 
			// player2Label
			// 
			this.player2Label.Font = new System.Drawing.Font("Comic Sans MS", 9.75F, System.Drawing.FontStyle.Regular, System.Drawing.GraphicsUnit.Point, ((System.Byte)(0)));
			this.player2Label.ForeColor = System.Drawing.Color.FromArgb(((System.Byte)(255)), ((System.Byte)(255)), ((System.Byte)(200)));
			this.player2Label.Location = new System.Drawing.Point(8, 64);
			this.player2Label.Name = "player2Label";
			this.player2Label.Size = new System.Drawing.Size(64, 23);
			this.player2Label.TabIndex = 3;
			this.player2Label.Text = "Player 2";
			this.player2Label.TextAlign = System.Drawing.ContentAlignment.MiddleLeft;
			// 
			// score1Text
			// 
			this.score1Text.BackColor = System.Drawing.Color.FromArgb(((System.Byte)(255)), ((System.Byte)(255)), ((System.Byte)(200)));
			this.score1Text.Font = new System.Drawing.Font("Comic Sans MS", 9.75F, System.Drawing.FontStyle.Bold, System.Drawing.GraphicsUnit.Point, ((System.Byte)(0)));
			this.score1Text.ForeColor = System.Drawing.Color.Black;
			this.score1Text.Location = new System.Drawing.Point(80, 32);
			this.score1Text.Name = "score1Text";
			this.score1Text.ReadOnly = true;
			this.score1Text.Size = new System.Drawing.Size(40, 26);
			this.score1Text.TabIndex = 0;
			this.score1Text.Text = "0";
			this.score1Text.TextAlign = System.Windows.Forms.HorizontalAlignment.Center;
			// 
			// player1Label
			// 
			this.player1Label.Font = new System.Drawing.Font("Comic Sans MS", 9.75F, System.Drawing.FontStyle.Regular, System.Drawing.GraphicsUnit.Point, ((System.Byte)(0)));
			this.player1Label.ForeColor = System.Drawing.Color.FromArgb(((System.Byte)(255)), ((System.Byte)(255)), ((System.Byte)(200)));
			this.player1Label.Location = new System.Drawing.Point(8, 32);
			this.player1Label.Name = "player1Label";
			this.player1Label.Size = new System.Drawing.Size(64, 23);
			this.player1Label.TabIndex = 1;
			this.player1Label.Text = "Player 1";
			this.player1Label.TextAlign = System.Drawing.ContentAlignment.MiddleLeft;
			// 
			// statusBar
			// 
			this.statusBar.Font = new System.Drawing.Font("Century Gothic", 9.75F, System.Drawing.FontStyle.Regular, System.Drawing.GraphicsUnit.Point, ((System.Byte)(0)));
			this.statusBar.Location = new System.Drawing.Point(0, 381);
			this.statusBar.Name = "statusBar";
			this.statusBar.Panels.AddRange(new System.Windows.Forms.StatusBarPanel[] {
																						 this.statusBarText,
																						 this.statusBarCount});
			this.statusBar.ShowPanels = true;
			this.statusBar.Size = new System.Drawing.Size(514, 22);
			this.statusBar.TabIndex = 2;
			this.statusBar.Text = "Click File->New to start game";
			// 
			// statusBarText
			// 
			this.statusBarText.BorderStyle = System.Windows.Forms.StatusBarPanelBorderStyle.None;
			this.statusBarText.Text = "Click File->New to start  game";
			this.statusBarText.Width = 300;
			// 
			// statusBarCount
			// 
			this.statusBarCount.AutoSize = System.Windows.Forms.StatusBarPanelAutoSize.Spring;
			this.statusBarCount.Width = 198;
			// 
			// cheatButton
			// 
			this.cheatButton.Font = new System.Drawing.Font("Walt Disney Script v4.1", 15.75F, System.Drawing.FontStyle.Bold, System.Drawing.GraphicsUnit.Point, ((System.Byte)(0)));
			this.cheatButton.ForeColor = System.Drawing.Color.FromArgb(((System.Byte)(255)), ((System.Byte)(255)), ((System.Byte)(200)));
			this.helper.SetHelpKeyword(this.cheatButton, "cheat");
			this.helper.SetHelpString(this.cheatButton, "See how the computer remembers the cards");
			this.cheatButton.Location = new System.Drawing.Point(8, 320);
			this.cheatButton.Name = "cheatButton";
			this.helper.SetShowHelp(this.cheatButton, true);
			this.cheatButton.Size = new System.Drawing.Size(128, 40);
			this.cheatButton.TabIndex = 3;
			this.cheatButton.Text = "Cheat";
			this.cheatButton.Click += new System.EventHandler(this.button1_Click);
			// 
			// menuItem4
			// 
			this.menuItem4.Index = -1;
			this.menuItem4.Text = "";
			// 
			// statusTimer
			// 
			this.statusTimer.Enabled = true;
			this.statusTimer.Interval = 200;
			this.statusTimer.Tick += new System.EventHandler(this.statusTimer_Tick);
			// 
			// moveTimer
			// 
			this.moveTimer.Enabled = true;
			this.moveTimer.Tick += new System.EventHandler(this.moveTimer_Tick);
			// 
			// buttonTest
			// 
			this.buttonTest.Location = new System.Drawing.Point(24, 264);
			this.buttonTest.Name = "buttonTest";
			this.buttonTest.TabIndex = 4;
			this.buttonTest.Text = "Test";
			this.buttonTest.Visible = false;
			this.buttonTest.Click += new System.EventHandler(this.buttonTest_Click);
			// 
			// MemoryForm
			// 
			this.AutoScaleBaseSize = new System.Drawing.Size(7, 25);
			this.BackColor = System.Drawing.Color.CornflowerBlue;
			this.ClientSize = new System.Drawing.Size(514, 403);
			this.Controls.AddRange(new System.Windows.Forms.Control[] {
																		  this.buttonTest,
																		  this.cheatButton,
																		  this.statusBar,
																		  this.scoreGroup});
			this.Cursor = System.Windows.Forms.Cursors.Hand;
			this.Font = new System.Drawing.Font("Walt Disney Script v4.1", 14.25F, System.Drawing.FontStyle.Bold, System.Drawing.GraphicsUnit.Point, ((System.Byte)(0)));
			this.ForeColor = System.Drawing.Color.FromArgb(((System.Byte)(255)), ((System.Byte)(255)), ((System.Byte)(200)));
			this.FormBorderStyle = System.Windows.Forms.FormBorderStyle.FixedSingle;
			this.Icon = ((System.Drawing.Icon)(resources.GetObject("$this.Icon")));
			this.MaximizeBox = false;
			this.Menu = this.mainMenu1;
			this.Name = "MemoryForm";
			this.SizeGripStyle = System.Windows.Forms.SizeGripStyle.Hide;
			this.Text = "Icon Memory Game";
			this.MouseUp += new System.Windows.Forms.MouseEventHandler(this.OnMouseUp);
			this.scoreGroup.ResumeLayout(false);
			((System.ComponentModel.ISupportInitialize)(this.statusBarText)).EndInit();
			((System.ComponentModel.ISupportInitialize)(this.statusBarCount)).EndInit();
			this.ResumeLayout(false);

		}
		#endregion

		#region IGameBoardDisplay Interface Methods
		/// <summary>
		/// Draw the Game Board (reqd by IGameBoardDisplay Interface
		/// </summary>
		public void DrawGameBoard(CCard[,] cardArray)
		{
			int cardHeight = m_gameBoardRect.Height / CGameBoard.NUM_ROWS;
			int cardWidth = m_gameBoardRect.Width / CGameBoard.NUM_COLUMNS;

			// since the card is not the full size of its grid, offset the origin
			// to center the cards in the draw rectangle
			int offsetLeft = (cardWidth - cardArray[0,0].CardSize.Width) / 2;
			int offsetTop = (cardHeight - cardArray[0,0].CardSize.Height) / 2;

			for (int i = 0; i < CGameBoard.NUM_COLUMNS; i++)
				for (int j = 0; j < CGameBoard.NUM_ROWS; j++)
				{
					Point loc = new Point(m_gameBoardRect.Left + offsetLeft + (cardWidth) * j,
						m_gameBoardRect.Top + offsetTop + (cardHeight) * i);
					cardArray[i,j].DrawLocation = loc;
					cardArray[i,j].Draw(graphicsObject);
				}
		}

		/// <summary>
		/// Redraw a single card on the Game Board (reqd by IGameBoardDisplay Interface
		/// </summary>
		public void UpdateGameBoard(CCard card)
		{
			card.Draw(graphicsObject);
		}

		#endregion

		#region Event Handlers
		/// <summary>
		/// Event Handler that paints the game board
		/// </summary>
		protected override void OnPaint(System.Windows.Forms.PaintEventArgs e)
		{
			/// draw a rectangle with round corners
			const int RADIUS = 10;
			SolidBrush brush = new SolidBrush(Color.FromArgb(255, 255, 200));	// LightYellow
			Pen pen = new Pen(Color.Navy, 1);
			GraphicsPath cardTable = new GraphicsPath();

			// create the path
			cardTable.AddArc(m_gameBoardRect.Left, m_gameBoardRect.Top, RADIUS, 
							RADIUS, 270, -90);
			cardTable.AddLine(m_gameBoardRect.Left, m_gameBoardRect.Top + RADIUS,
							m_gameBoardRect.Left, m_gameBoardRect.Bottom - RADIUS);
			cardTable.AddArc(m_gameBoardRect.Left, m_gameBoardRect.Bottom - RADIUS, 
							RADIUS, RADIUS, 180, -90);
			cardTable.AddLine(m_gameBoardRect.Left + RADIUS, m_gameBoardRect.Bottom,
							m_gameBoardRect.Right - RADIUS, m_gameBoardRect.Bottom);
			cardTable.AddArc(m_gameBoardRect.Right - RADIUS, m_gameBoardRect.Bottom - RADIUS, 
							RADIUS, RADIUS, 90, -90);
			cardTable.AddLine(m_gameBoardRect.Right, m_gameBoardRect.Bottom - RADIUS,
							m_gameBoardRect.Right, m_gameBoardRect.Top + RADIUS);
			cardTable.AddArc(m_gameBoardRect.Right - RADIUS, m_gameBoardRect.Top, RADIUS, 
							RADIUS, 0, -90);
			cardTable.AddLine(m_gameBoardRect.Right - RADIUS, m_gameBoardRect.Top,
							m_gameBoardRect.Left + RADIUS, m_gameBoardRect.Top);
			cardTable.CloseFigure();

			// fill the path and add a border
			e.Graphics.FillPath(brush, cardTable);
			e.Graphics.DrawPath(pen, cardTable);

			/// draw the cards
			theGame.GameBoard.Draw();
			Trace.WriteLine("OnPaint() called Draw()");
		}

		/// <summary>
		/// Event Handler that processes when a user selects a card
		/// </summary>
		private void OnMouseUp(object sender, System.Windows.Forms.MouseEventArgs e)
		{
			if (theGame.WhoseTurn == null || theGame.WhoseTurn.AcceptInput() == false // don't allow mouse clicking unless a user is the current player
				|| (theGame.LastTwoMoves.location1.column != -1))							// or the cards haven't been flipped yet
				return;

			// get the point that was just clicked
			Point selected = new Point(e.X, e.Y);
			rowColumn = GetRowColumn(selected);
			
			if (rowColumn.column != -1 && rowColumn.row != -1)
			{
				// report the move to the game engine
				theGame.RecordMove(rowColumn);
			}
			m_moveTimerCount = 0;
		}


		/// <summary>
		/// Event Handler that handles the New 2 Player Game Menu Selection
		/// </summary>
		private void menuNew2P_Click(object sender, System.EventArgs e)
		{	
			StartGame(gameType.TwoPlayer);
		}

		/// <summary>
		/// Event Handler that handles the New 1 Player Game Menu Selection
		/// </summary>
		private void menuNew1P_Click(object sender, System.EventArgs e)
		{
			StartGame(gameType.OnePlayer);
		}
		
		/// <summary>
		/// Event Handler that processes the New 1 Player vs. Computer Game Menu Selection
		/// </summary>
		private void menuNew1PvC_Click(object sender, System.EventArgs e)
		{
			StartGame(gameType.OnePlayerVersusComputer);
		}

		/// <summary>
		/// Event Handler tha processes the Exit menu selection
		/// </summary>
		private void menuFileExit_Click(object sender, System.EventArgs e)
		{
			Application.Exit();

			statusTimer.Dispose();
		}

		/// <summary>
		/// Event Handler that processes the difficulty selection menu items
		/// </summary>
		private void menuOptionsDifficultyX_Click(object sender, System.EventArgs e)
		{
			// set each player's IQ
			foreach (CPlayer player in theGame.PlayerArray)
				if (player != null)
					player.IQ = ((System.Windows.Forms.MenuItem) sender).Index;
			
			// uncheck all menu items
			foreach (MenuItem item in this.menuOptionsDifficulty.MenuItems)
				item.Checked = false;

			// check the selected menu item
			((System.Windows.Forms.MenuItem) sender).Checked = true;
		}

		/// <summary>
		/// Event Handler that processes the status timer tick
		/// </summary>
		private void statusTimer_Tick(object sender, System.EventArgs e)
		{
			statMon.Update();
		}

		/// <summary>
		/// Event Handler that processes the move timer tick
		/// </summary>
		private void moveTimer_Tick(object sender, System.EventArgs e)
		{
			// stop the game when its over
			if (theGame.GameBoard.CardsTurnedOver >= CGameBoard.TOTAL_CARDS)
			{
				moveTimer.Stop();
				theGame.GameOver = true;
				return;
			}

			// check if enough time has passed since last action
			if (m_moveTimerCount < m_delayTime)
			{
				m_moveTimerCount++;
				return;
			}

			// check if any cards need flipping
			if (theGame.LastTwoMoves.location1.column != -1)
			{
				Match temp = theGame.LastTwoMoves;
				theGame.GameBoard.TurnOverCard(temp.location1.column, temp.location1.row, false);
				theGame.GameBoard.TurnOverCard(temp.location2.column, temp.location2.row, false);
				theGame.LastTwoMoves = new Match(new Position(-1, -1), new Position(-1, -1), false);
				m_moveTimerCount = 0;
				return;
			}

			// if it is the user's turn, just exit
			if (theGame.WhoseTurn == null || theGame.WhoseTurn.AcceptInput() == true)	
			{
				m_moveTimerCount = 0;
				return;
			}

			theGame.RecordMove(theGame.WhoseTurn.GetMove());

			m_moveTimerCount = 0;
		}

		/// <summary>
		/// Event Handler that processes the Cheat Button click
		/// </summary>
		private void button1_Click(object sender, System.EventArgs e)
		{
			// player 2 must exist and not be a human
			if (theGame.PlayerArray[1] != null && !theGame.PlayerArray[1].AcceptInput())
				MessageBox.Show( (theGame.PlayerArray[1]).ShowStringArray());
		}

		/// <summary>
		/// Event Handler that processes the speed selection menu items
		/// </summary>
		private void menuOptionsSpeed_Click(object sender, System.EventArgs e)
		{
			m_delayTime = 12 - ((System.Windows.Forms.MenuItem) sender).Index * 4;

			// uncheck all menu items
			foreach (MenuItem item in this.menuOptionsSpeed.MenuItems)
				item.Checked = false;

			// check the selected menu item
			((System.Windows.Forms.MenuItem) sender).Checked = true;

			Trace.WriteLine("Speed changed to: " + m_delayTime.ToString());
		}

		/// <summary>
		/// Event Handler that processes the Help menu items
		/// </summary>
		private void menuHelp_Click(object sender, System.EventArgs e)
		{
			if (sender == menuHelpTopics)
				Help.ShowHelp(this, "Help\\Memory Help.htm");

			if (sender == menuHelpAbout)
				MessageBox.Show("Icon Memory Game Rev. 1.1.0\n\nby Stan Dewan\nwww.thestrangestofplaces.net",
					"About Icon Memory Game");
		}

		/// <summary>
		/// Event Handler that processes the High Scores Menu item click
		/// </summary>
		private void menuFileHighScores_Click(object sender, System.EventArgs e)
		{
			MessageBox.Show(theGame.ScoresDB.ToString(), "High Scores");
		}


		#endregion

		#region Utility Functions
		/// <summary>
		/// Method that starts a new game
		/// </summary>
		/// <param name="type">
		/// the type of game being started
		/// </param>
		private void StartGame(gameType type)
		{
			// initialize a new set of game variables
			theGame.StartGame(type);

			// enable or disable the cheat button
			if (theGame.PlayerArray[1] != null && !theGame.PlayerArray[1].AcceptInput())
				this.cheatButton.Enabled = true;
			else
				this.cheatButton.Enabled = false;
			
			// start the move and status timers ticking
			moveTimer.Start();
			statMon.Reset();

			// redraw the screen
			Invalidate();
		}

		/// <summary>
		/// returns the column (X) and row (Y) that the passed point lies in - (-1,-1) if nothing selected
		/// </summary>
		protected Position GetRowColumn(Point point)
		{
			Position output = new Position(-1,-1);
			// check each card to see if the point lies within it
			for (int i = 0; i < CGameBoard.NUM_COLUMNS; i++)
				for (int j = 0; j < CGameBoard.NUM_ROWS; j++)
				{
					if (theGame.GameBoard.CardArray[i,j].GetBounds().Contains(point))
					{
						output.column = i;
						output.row = j;
						Invalidate(theGame.GameBoard.CardArray[i,j].GetBounds());
					}
				}
			return output;
		}

		/// <summary>
		/// Method to highlight the current player or display a status bar message
		/// </summary>
		public void UpdateStatus(int playerNumber, string message)
		{
			if (playerNumber == -1)
			{
				this.player1Label.Font = new Font(player1Label.Font.FontFamily, player1Label.Font.Size,FontStyle.Regular);
				this.player2Label.Font = new Font(player2Label.Font.FontFamily, player2Label.Font.Size,FontStyle.Regular);
			}
			if (playerNumber == 1)
			{
				this.player1Label.Font = new Font(player1Label.Font.FontFamily, player1Label.Font.Size,FontStyle.Bold);
				this.player2Label.Font = new Font(player2Label.Font.FontFamily, player2Label.Font.Size,FontStyle.Regular);
			}
			if (playerNumber == 2)
			{
				this.player1Label.Font = new Font(player1Label.Font.FontFamily, player1Label.Font.Size,FontStyle.Regular);
				this.player2Label.Font = new Font(player2Label.Font.FontFamily, player2Label.Font.Size,FontStyle.Bold);
			}

			this.statusBarText.Text = message;

			// format the cards count string
			string counter = String.Format("{0:G} of {1:G} Cards Turned Over",
				theGame.GameBoard.CardsTurnedOver,
				CGameBoard.TOTAL_CARDS);

			// update the scores
			if (theGame.PlayerArray[0] != null)
				score1Text.Text = theGame.PlayerArray[0].Score.ToString();
			else
				score1Text.Text = "-";
			if (theGame.PlayerArray[1] != null)
				score2Text.Text = theGame.PlayerArray[1].Score.ToString();
			else
				score2Text.Text = "-";

			this.statusBarCount.Text = counter;
		}

		/// <summary>
		/// Method that enables/ disables controls as appropriate
		/// </summary>
		public void UpdateControls(int flags)
		{
			// check if the flags have changed
			if (flags == lastControlFlags)
				// if not, return immediately
				return;

			// enable / disable the difficulty menus
			if ((flags & StatusMonitor.MENU_DIFFICULTY) != 0)
			{
				this.menuOptionsDifficulty0.Enabled = true;
				this.menuOptionsDifficulty1.Enabled = true;
				this.menuOptionsDifficulty2.Enabled = true;
				this.menuOptionsDifficulty3.Enabled = true;
				this.menuOptionsDifficulty4.Enabled = true;
				this.menuOptionsDifficulty5.Enabled = true;
			}
			else
			{
				this.menuOptionsDifficulty0.Enabled = false;
				this.menuOptionsDifficulty1.Enabled = false;
				this.menuOptionsDifficulty2.Enabled = false;
				this.menuOptionsDifficulty3.Enabled = false;
				this.menuOptionsDifficulty4.Enabled = false;
				this.menuOptionsDifficulty5.Enabled = false;
			}

			// remember the flags for next time
			lastControlFlags = flags;
		}

		#endregion

		/// <summary>
		/// Clean up any resources being used.
		/// </summary>
		protected override void Dispose( bool disposing )
		{
			if( disposing )
			{
				if(components != null)
				{
					components.Dispose();
				}
			}
			base.Dispose( disposing );
		}
	
		/// <summary>
		/// The main entry point for the application.
		/// </summary>
		[STAThread]
		static void Main() 
		{

			Application.Run(new MemoryForm());
		}

		 
		// Test Code

		// Import the DLL that supports the PlaySound() function
		[System.Runtime.InteropServices.DllImport("Winmm.dll")]
		public static extern bool PlaySound(byte[] fileName, int mustBeNull, long flags);
		[System.Runtime.InteropServices.DllImport("Winmm.dll")]
		public static extern bool PlaySound(string fileName, int mustBeNull, long flags);

		/// <summary>
		/// Event Handler that processes the Test button click (for testing new code)
		/// </summary>
		private void buttonTest_Click(object sender, System.EventArgs e)
		{

//			System.Reflection.Assembly thisAsm = System.Reflection.Assembly.GetExecutingAssembly();

			Cursor.Current = Cursors.WaitCursor;
	//		PlaySound("CMemoryGame.flip.wav", thisAsm.GetModule("CMemoryGame.flip.wav"), 0x00040004L | 0x0001L);

//			String[] test2 = thisAsm.GetManifestResourceNames();
//			System.IO.Stream myStream = thisAsm.GetManifestResourceStream( "TSOP.Games.IconMemoryGame.flip.wav" );
//			byte[] byteWavFile = new Byte[ myStream.Length ];
//			myStream.Read( byteWavFile, 0, ( int ) myStream.Length );


//			PlaySound(byteWavFile, 0, (long) TSOP.Multimedia.SoundPlayer.Flags.SND_MEMORY | (long) TSOP.Multimedia.SoundPlayer.Flags.SND_ASYNC);


			// try it with the new class
			SoundResourcePlayer sndRes = new SoundResourcePlayer();

			sndRes.Path = "TSOP.Games.IconMemoryGame.";

			sndRes.PlayAsync();

			sndRes.PlaySync("nomatch.wav");

			sndRes.PlayAsync("computermatches.wav");

			Cursor.Current = Cursors.Default;
		}





	}
}
