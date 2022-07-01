#include <iostream>
#include<bits/stdc++.h>
using namespace std;

vector<vector<int>> nbrs = {{1,0},{0,1},{-1,0},{0,-1}};
vector<char> dir = {'r','d','l','u'};
void dfs(vector<vector<int>>& grid, int i, int j, vector<vector<bool>>& visited, string& s){
  visited[i][j] = true;
  for(int k=0;k<4;k++){
    int x = i + nbrs[k][0];
    int y = j + nbrs[k][1];

    if(x<0 || y<0 || x>=grid.size() || y>=grid[0].size() || visited[x][y] || grid[x][y]==0)
      continue;
    s += dir[k];
    dfs(grid,x,y,visited,s);
  }
  s += '@';
}

int dis(vector<vector<int>>& grid){
  int res = 0, n = grid.size(), m = grid[0].size();
  vector<vector<bool>> visited(n,vector<bool>(m,false));
  unordered_set<string> s;
  for(int i=0;i<n;i++){
    for(int j=0;j<m;j++){
      if(grid[i][j]==1 && !visited[i][j]){
        string island = "";
        dfs(grid,i,j,visited,island);
        if(s.find(island)==s.end()){
          s.insert(island);
        }
      }
    }
  }
  return (int) s.size();
}

int main() {
	vector<vector<int>> grid = {{1,1,0,1,1},{1,0,0,0,0},{0,0,0,0,1},{1,1,0,1,1}};
  cout<<dis(grid)<<endl;
	return 0;
}
