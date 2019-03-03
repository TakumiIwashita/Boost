## 配列の歴史

- **イテレータ**

- **BOOST_FOREACH**

  - for each文のマクロ

  - シーケンスの各要素がループ変数に格納され、処理される

  - <boost/foreach.hpp>をincludeする

    ```c++
    const std::vector<int> v;
    
    BOOST_FOREACH (int x, v) { 
    std::cout << x << std::endl;
    }
    ```

    

- **範囲for文**

  ```c++
  for (int x : v) {}
  ```

  - 範囲for文とFOR_EACHの違い
    - `BOOST_FOREACH`マクロは、イテレータの組(`std::pair<begin-iter, end-iter>`)をサポートしている
    - 範囲`for`文は、要素の変数を範囲`for`文で定義しなければならない

- **for_each文**

  - 範囲の全ての要素に、指定された関数を適用する
  -  <boost/range/algorithm/for_each.hpp>をincludeする

  ```c++
  void disp(const std::string& s)
  {
  	std::cout << s << std::endl;
  }
  
  int main()
  {
  	const std::string s = "abc,123,xyz";
  
  	std::vector<std::string> result;
  	boost::algorithm::split(result, s, boost::is_any_of(",")); // カンマで分割
  
  	boost::for_each(result, disp);
  }
  ```

  

- [NSFileManager ファイルに関する操作](http://atmarkplant.com/nsfilemanager/)

