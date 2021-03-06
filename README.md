# SetMatrixZero
C++ code to set a 2d array to zero
Optimised Solution using O(m+n) space and Time Complexity of O(m*n)
 void setZeroes(vector<vector<int>>& matrix) {
        int rows = matrix.size(); int col = matrix[0].size();
        int a1[rows] ;
        int a2[col] ;
        for(int i=0;i<rows;i++)
        {
            a1[i] = -1;
        }
         for(int i=0;i<col;i++)
        {
            a2[i] = -1;
        }
        for(int i=0;i<rows;i++){
            for(int j=0;j<col;j++){
                if(matrix[i][j]==0){
                    a1[i]=0;
                    a2[j]=0;
                }
            }
        }
         for(int i=0;i<rows;i++){
            for(int j=0;j<col;j++){
                if(a1[i]==0 || a2[j] == 0){
                    matrix[i][j]=0;
                }
            }
        }
    }
//Best solution using constant space and Time Complexity of O(m*n)
    void setZeroes(vector<vector<int>>& matrix) {
         int rows = matrix.size(); int col = matrix[0].size();
        int col0 = 1;
         for(int i=0;i<rows;i++){
             if(matrix[i][0]==0) col0 = 0;
            for(int j=1;j<col;j++){
                if(matrix[i][j]==0){
                    matrix[i][0]=0;
                    matrix[0][j]=0;
                }
            }
        }
          for(int i=rows-1;i>=0;i--){
            for(int j=col-1;j>0;j--){
                if(matrix[i][0]==0 || matrix[0][j]==0){
                    matrix[i][j]=0;
                }
            }
              if(col0 == 0) matrix[i][0]=0;
        }
    }
