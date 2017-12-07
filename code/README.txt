#####################################################################################################
#   GIFT: Guided and Interpretable Factorization for Tensors - Applications to Human Cancer Analytics
#   
#   Authors: Sejoon Oh (ohhenrie@snu.ac.kr), Seoul National University
#            Jungwoo Lee (muon9401@gmail.com), Seoul National University
#            Lee Sael (sael@sunykorea.ac.kr), The State University of New York (SUNY) Korea
#   
#   Version : 1.0
#   Date: 2017-11-30
#   Main contact: Sejoon Oh
#
#   This software is free of charge under research purposes.
#   For commercial purposes, please contact the author.
######################################################################################################

1. Introduction

    GIFT is a Guided and Interpretable Factorization for Tensors. GIFT provides interpretable factor matrices by 
    encoding prior knowledge as a regularization term in its objective function.
    
    Please refer to the following website for the details of GIFT.
  	https://github.com/leesael/GIFT

2. Usage
	
	[Step 1] Install Armadillo, LAPACK, and BLAS libraries.

		GIFT requires Armadillo and OpenMP libraries.

		Armadillo library is available at the lib directory or http://arma.sourceforge.net/download.html.

		Notice that Armadillo needs LAPACK and BLAS libraries, and they are also available at the lib directory.

		OpenMP version 2.0 or higher is required for GIFT. (It is installed by default if you use gcc/g++ compiler)
 	
 	[Step 2] Compile and run GIFT.

		If you successfully install all libraries, "make stf, ptf, or gift" command will create the corresponding executable file.

		The executable file takes 6 (GIFT and Silenced-TF) or 5 (P-Tucker) arguments, which are the path of an input tensor file, path of a mask matrix (GIFT and Silenced-TF only), path of a directory for storing results, tensor order (N), lambda, and tensor ranks (N elements). The arguments MUST BE valid and in the above order.

		ex1) ./gift input.txt mask.txt result/ 3 0.01 10 20 30
		ex2) ./ptf input.txt result/ 3 0.01 10 20 30

		Note that an input tensor uses base-1 indexing and mask matrices use base-0 indexing. Mask matrices should be given in a single file, where the first column indicates a mask matrix number and the rest of columns are indices in a mask matrix.
		
		If you put the command properly, GIFT and other methods will write all values of factor matrices and a core tensor in the result directory set by an argument. (PLEASE MAKE SURE THAT YOU HAVE A WRITE PERMISSION TO THE RESULT DIRECTORY!)

		ex) result/FACTOR1, result/CORETENSOR