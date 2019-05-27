```rust
impl Solution {
    pub fn generate_matrix(n: i32) -> Vec<Vec<i32>> {
        let n = n as usize;
        let mut matrix = vec![vec![0; n]; n];
        let mut k = 0;
        let mut ia = 0;
        let mut ib = n;
        let mut ja = 0;
        let mut jb = n;
        while ia < ib {
            for j in ja..jb {
                k += 1;
                matrix[ia][j] = k;
            }
            ia += 1;
            for i in ia..ib {
                k += 1;
                matrix[i][jb - 1] = k;
            }
            jb -= 1;
            for j in (ja..jb).rev() {
                k += 1;
                matrix[ib - 1][j] = k;
            }
            ib -= 1;
            for i in (ia..ib).rev() {
                k += 1;
                matrix[i][ja] = k;
            }
            ja += 1;
        }
        matrix
    }
}
```
