##Bootstrap
* 布局容器container和`container-fluid`分别代表固定宽度的响应式布局和100%viewport
* list
    * `list-gruop` `list-group-item` `list-group-item-success `list-inline`
    * `breadcrumb`

            <ul class="breadcrumb">
                <li><a href="#">Level 1</a></li>
                <li><a href="#">Level 2</a></li>
                <li class="active">Level 3</li>
            </ul>
    * `pagination`

            <ul class="pagination pagination-sm">
                <li class="disabled"><a href="#">&laquo;</a></li>
                <li class="active"><a href="#">1</a></li>
                <li><a href="#">2</a></li>
                <li><a href="#">3</a></li>
                <li><a href="#">&laquo;</a></li>
            </ul>
    * `pager`
    * `nav` `nav-table` `nav-nav-pills`

* span类---`ico` `label` `badge`
* button
    * `data-toggle="button"`设置切换状态
* input
        
        <div class="input-group">
            <input type="text" class="form-control">
            <span class="input-group-btn">
                <button  type="button" class="btn btn-default">Action</button>
                <button type="button" class="btn btn-default"></button>
            </span>
        </div>

* dropdown

        <div class="dropdown">
                <a href="#"  data-toggle="dropdown" class="dropdown-toggle"><b class="caret"></b></a>
                <ul class="dropdown-menu">
                    <li><a href="#" class="btn-primary">Action 1</a></li>
                    <li><a href="#" class="btn-primary">Action 2</a></li>
                </ul>
        </div>