Ninja
=====
using System;
using System.Collections.Generic;
using System.ComponentModel;
using System.Data;
using System.Drawing;
using System.Drawing.Imaging;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using System.Windows.Forms;
using System.IO;

namespace Ninja
{

    public partial class Form1 : Form
    {
        //deklaracja map bitowych
        private Bitmap obrazek;
        private Bitmap obrazekKopia;
        //deklaracja stringow dla porownywania
        string obrazS;
        string obrazKopiaS;
        
        public Form1()
        {
            InitializeComponent();


            //Ukrycie elementow
            button1.Visible = false;
            button2.Visible = false;
            label1.Visible = false;
            pictureBox1.Visible = false;
            pictureBox2.Visible = false;
            button3.Visible = false;

        }

        //deklaracje komponentow

        //funkcja zamykajaca program
        private void zakończToolStripMenuItem1_Click(object sender, EventArgs e)
        {
            Close();
        }

        //wyswietla informacje o programie
        private void oProgramieToolStripMenuItem_Click(object sender, EventArgs e)
        {
            MessageBox.Show("Ninja version 1.00\n\tCopyright(c) 2013\n\t\tautor: Wojciech Rodzeń","O programie");
        }

        //aktywowanie kontrolek do operacji na obrazach
        private void obrazToolStripMenuItem_Click(object sender, EventArgs e)
        {
            label2.Visible = false;
            button1.Visible = true;
            button2.Visible = true;
            button3.Visible = true;
            label1.Visible = true;
            pictureBox1.Visible = true;
            pictureBox2.Visible = true;
        }

        /*
        //operacje na bitmapach, wczytywanie i zapisywanie
        public Bitmap Obrazek
        {
            get
            {
                return obrazek;
            }
            set
            {
                obrazek = value;
            }
        }
        //wczytywanie kopii obrazka
        public Bitmap ObrazekKopia
        {
            get
            {
                return obrazekKopia;
            }
            set
            {
                obrazek = value;
            }
        }*/

        //wczytanie obrazu nr.1
        private void button1_Click(object sender, EventArgs e)
        {
            String filter = "JPEG files (*.jpg)|*.jpg| Bitmaps (*.bmp)|*.bmp";

            OpenFileDialog dlg = new OpenFileDialog();
            dlg.Multiselect = false;
            if (filter.Length > 0) { dlg.Filter = filter; }

            if (dlg.ShowDialog(this) != DialogResult.Cancel)
            {
                if (dlg.FileName != null)
                {
                    pictureBox2.Image = obrazek = new Bitmap(dlg.FileName);
                }
            }
        }


        private void label2_Click(object sender, EventArgs e)
        {
            
        }

        //wczytanie obrazu nr.2
        private void button2_Click(object sender, EventArgs e)
        {
            String filter = "JPEG files (*.jpg)|*.jpg| Bitmaps (*.bmp)|*.bmp";

            OpenFileDialog dlg = new OpenFileDialog();
            dlg.Multiselect = false;
            if (filter.Length > 0) { dlg.Filter = filter; }

            if (dlg.ShowDialog(this) != DialogResult.Cancel)
            {
                if (dlg.FileName != null)
                {
                    pictureBox1.Image = obrazekKopia = new Bitmap(dlg.FileName);
                }
            }
        }

        //zlecenie porownania
        private void button3_Click(object sender, EventArgs e)
        {
            MessageBox.Show("rezultat","Rezultat");
        }

        //funkcja porownujaca
        unsafe private void porownuj(Bitmap obrazek, Bitmap obrazek2)
        {
            
            bool[,] rozne = new bool[obrazek.Width,obrazek.Height];
            for (int i = 0; i < obrazek.Width; i++)
            {
                for (int j = 0; j < obrazek.Height; j++)
                {
                    if()
                }
            }

        }


    }
}
