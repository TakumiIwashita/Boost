◯ptreeから値を取得するアレコレ方法
https://blog.kmc.gr.jp/entry/2015/12/21/183846
ptreeから値を取得する
ptreeからtag内のintの値（XMLでは<tag>value</tag>のvalue）を得る方法の一例

ptree.get<int>("tag");
ptree,get_optional<int>("tag");
ptree.get("tag", 0);
ptree.get_child("tag").get_value<int>();


◯ptreeから値を取得するアレコレ方法：その2
https://www.boost.org/doc/libs/1_69_0/doc/html/property_tree/accessing.html
・The throwing version (get):
ptree pt;
float v = pt.get<float>("a.path.to.float.value");

・The default-value version (get):
ptree pt;
float v = pt.get("a.path.to.float.value", -1.f);

・The optional version (get_optional):
ptree pt;
boost::optional<float> v = pt.get_optional<float>("a.path.to.float.value");


◯ptreeの中身を探す方法
http://www.ce.unipr.it/~medici/boost_ptree.html
Search for a node
boost::property_tree::ptree::const_assoc_iterator i_pts = parent.find("points");
if(parent.not_found() != i_pts) {
  const boost::property_tree::ptree & pts = (*i_pts).second;
}
