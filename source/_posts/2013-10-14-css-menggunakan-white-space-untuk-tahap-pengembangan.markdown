---
layout: post
title: "CSS: Menggunakan White Space Untuk Tahap Pengembangan"
date: 2013-10-14 11:25
comments: true
categories: CSS

keywords: "css, css3, snippet, kode, white space, indentasi, sass, html"
description: "Tidak ada benar dan salah dan saya tidak mencari itu. Dengan atau tanpa alasan, setiap orang, terlebih para front-end web developer memiliki gaya menulis CSS yang berbeda."
---

Saya sering melihat beberapa gaya menulis kode CSS.  Tentu saja saya dapatkan dari orang lain. Bisa dari proyek (*side job*), dari pekerjaan saya sendiri atau hanya melihat dari *snippet code* yang ada di internet. 

Nah, ada kalanya saya melanjutkan pekerjaan dari tangan orang lain. Beberapa diantaranya tidak cocok dengan gaya saya. Berhenti sampai disini dulu, tidak cocok bukan berarti salah. Tidak ada benar dan salah dan saya tidak mencari itu. Dengan atau tanpa alasan, setiap orang, terlebih para front-end web developer memiliki gaya menulis CSS yang berbeda.

##Lalu mana yang saya sukai?

{% codeblock lang:css%}
#example { font-size:12px; font-family:"Helvetica Neue", Helvetica, Arial, sans-serif; font-weight:normal; padding:3px; color:#777; background:#fff url('../images/bg-input.png') repeat-x 0px 0px; border-top:solid 1px #aaa; border-left:solid 1px #aaa; border-bottom:solid 1px #ccc; border-right:solid 1px #ccc; -webkit-border-radius:3px; -moz-border-radius:3px; border-radius:3px; outline:0; min-width:200px }
{% endcodeblock %}

Seperti kode di atas, saya tidak menyukai kode seperti itu. Kenapa? Terlalu memanjang secara horisontal. Ketika saya ingin mengganti salah satu komponen saja, saya harus melakukan scroll ke kanan. Ini terkait orientasi saya. Saya dan mungkin kebanyakan orang memiliki orientasi scroll atas-bawah daripada melakukan scroll kanan-kiri. Pun dengan dengan pindai cepat. Jika kode tertulis secara horisontal, akan terasa agak sulit untuk mencari dan menemukan property dari selector yang akan diganti.

Bandingkan dengan gaya ini:

{% codeblock lang:css%}
#example { 
		font-size:12px; 
		font-family:"Helvetica Neue", Helvetica, Arial, sans-serif; 
		font-weight:normal; 
		padding:3px; 
		color:#777; 
		background:#fff url('../images/bg.png') repeat-x 0px 0px; 
		border-top:solid 1px #aaa; 
		border-left:solid 1px #aaa; 
		border-bottom:solid 1px #ccc; 
		border-right:solid 1px #ccc; 
		outline:0; 
		min-width:200px
			
			 -webkit-border-radius:3px; 
				-moz-border-radius:3px;
					 border-radius:3px;
}
{% endcodeblock %}

Meskipun ini adalah gaya yang mungkin bisa dibilang "standar" atau klasik, saya lebih menyukai kode CSS yang ditulis seperti di atas. Mudah untuk dipindai secara cepat dan saya tidak membuang-buang waktu hanya untuk mengganti satu properti.

Di dalam kode di atas, terdapat kode yang menggunakan ***Vendor Prefixes***. Saya melakukan indentasi untuk menuliskan kode CSS3. Karena saya menggunakan editor teks dengan Sublime Text, maka dengan penulisan seperti di atas, saya bisa mengoptimalkan fitur "*multiline editing*" yang tentu saja dapat meningkatkan efiensi saat bekerja dengan CSS.

##CSS Indentation

Semenjak mengenal SASS, saya kerap menuliskan kode dengan indentasi menurut hierarki-nya.

{% codeblock lang:css%}
/** Header **/
header {
    color: blue;
}
    hgroup {
        color: green;
    }
        hgroup h1 {
            line-height: 1.5;
        }
        hgroup h2 {
            font-size: 15px;
        }
        
    nav {
        background: purple;
    }
        nav ul {
            float: left;
        }
            nav ul li {
                font-size: 20px;
            }
                nav ul li a, nav ul li a:visited {
                    text-decoration: none;
                }
/** end of Header **/

/** Main **/                
.main {
    border: solid 1px #ccc;
}
{% endcodeblock %}

Mungkin kode di atas terasa agak "berlebihan", namun saya menyukai dan menerapkan banyak indentasi dalam proses pengembangan supaya *match* dengan markup HTML yang sudah saya buat sebelumnya. Sehingga saya lebih cepat untuk melakukan pemindaian selector dan properti.

##Lalu ... ?

Tahap pengembangan adalah tahap yang paling melelahkan dan ribet. Lupakan dulu masalah *performance* website. Performa dari siapa yang membuat kode juga perlu dipikirkan. Minimal dengan kode yang *readable* akan membuat para *front-end-ers* tidak mudah lelah dan efisien dari segi waktu pengerjaan. Toh, dengan kode yang tertulis rapi serta dengan dokumentasi yang baik nantinya kalau ingin melakukan optimasi kode atau ingin melakukan *debuging* akan mudah dilakukan.