# VMARC
John Fisher's wonderful VMARC utility

Years ago, John Fisher at Rensselaer Polytechnic Institute wrote the canonical CMS file-packaging utility, **VMARC**.  Since that time, there have been some changes needed, so around 1998 I took up support and did some Y2K work (although VMARC was largely Y2K-safe and had always been so, there were a few rough edges).  Anyway, here's what I've got to share.

I haven't worked with a VM/CMS system since 2002, but it appears that there haven't been any updates to VMARC since then.  Talk about stable software!  This code was originally hosted on GeoCities at http://www.GeoCities.com/RossPatterson/vmarc.

Because I can't guess how EBCDIC source files will be translated in a vintage 2020 Internet, I've uploaded the full source in the original EBCDIC to ./EBCDIC, and translated to ASCII in ./ASCII.  When in doubt, rely on the ./EBCDIC files.

## Licensing

John Fisher released his original code in 1989, long before the computing community became obsessed with licensing, before there was even a GNU Public License.  As a result, this repository is not covered by any Free Software or Open Source license, but is rather simply copyrighted code with rights granted from its original author.  John's original source file (VMARC ASSEMBLE) contains the following notice:

> Copyright (c) 1989, 1990, John S. Fisher, Troy, NY.
>
> Copyright (C) 1980 Columbia University, Carl Klass and Jeff Damens, CUCCA User Services, 12/80
>
> Permission is granted to use, copy, and distribute this program in any form as long as (1) this notice of copyright and distribution policy remain intact, (2) the distribution is made without charge above and beyond any reasonable fee to cover costs in making and delivering the copy, and (3) no additional restrictions are im-posed, either as to distribution or as to use.
>
> Note:  Specific permission is granted to Eric Thomas to use this program in his "Revised Listserv" program product, and to distribute this program as part of Listserv, whether or not any fee is collected.  Moreover, Eric Thomas may, at his discretion, modify the distribution policy stated above to prohibit redistribution of copies obtained as part of his Listserv product.

Similarly, his original documentation (VMARC SCRIPT) contains the following notice:

> Copyright (c) 1989, 1990, John S. Fisher, Troy, NY.
>
> Permission is granted to copy and distribute this documentation in any form to any one as long as (1) this notice of copyright and distribution policy remain intact, (2) the distribution is made without charge above and beyond any reasonable fee to cover costs in making and delivering the copy, and (3) no additional restrictions are imposed, either as to use or as to distribution.
>
> Permission is also granted to incorporate this program into other products, either as a tool used to package a product or as an added function to a product, as long as the presence of this program in the product does not contribute to the selling price of the product in any substantial way.

The VM Community has always honored John's wish.  We have shared his code widely, we have made small modifications as needed, and as far as I know, nobody has ever charged money for it or used it as the basis for any significant portion of some product.  Please do the same.

## "Recent" Updates To VMARC

The following updates have been issued "recently" (_i.e._ since I took over maintenance in 1998).  They apply on top of VMARC ASSEMBLE and all the prior updates (V1R2P002 through V1R2P020).
* Update VMARC V1R2P028, to support VM/370 R6 (for Hercules _et al._), courtesy of Peter J. Farley III (pjfarley3@yahoo.com).  Released 2002-05-14.
* Update VMARC V1R2P027, to tolerate RECFM=V archives for input.  Released 2000-08-21.
* Update VMARC V1R2P026, to ignore SFS zero-record files in VMARC PACK.  Released 2000-08-21.
* Update VMARC V1R2P025, allows assembly against MACLIBs from older levels of CMS. Released 1999-09-29.
* Update VMARC V1R2P024, fixes an obscure error in the source involving interrupt masking.  The object code always actually worked, but only by luck.  Released 1999-09-29.
* Update VMARC V1R2P023, documents the long-existing `ASKREPLACE`, `PROMPT` and `NEWREPLACE` options.  Released 1999-09-28.
* Update VMARC V1R2P022, corrects an input-file-reading problem that may occur running VMARC repeatedly under control of CMS Pipelines. Courtesy of The Piper, John Hartmann.  Released 1999-09-28.
* Update VMARC V1R2P021, changes to fully support Y2K.  Released 1998-09-23.
* An updated VMARC AUXUPD file with all updates including the above.

## The Whole Kit And Kaboodle
The entire `VMARC VMARC` package, containing all the source and all updates (including the "recent updates" listed above), and a compiled and linked MODULE.  Download as text and then do the following to unpack:
1. Issue the `PIPE < VMARC TXT | 64DECODE | FBLOCK 80 | > VMARC VMARC A F 80` command to reconstruct the VMARC file from the text file you downloaded.
1. Issue the `VMARC UNPK VMARC VMARC A * * <i>output_filemode</i>` command to extract all the source files from the VMARC file to the minidisk or SFS directory where you want to store them.