Previously, this would set the background color of the table header:

```
- (void)tableView:(UITableView *)tableView willDisplayHeaderView:(UIView *)view forSection:(NSInteger)section{    UITableViewHeaderFooterView *header = (UITableViewHeaderFooterView *)view;    header.backgroundView.backgroundColor = [UIColor blueColor];    [header.textLabel setTextColor:[UIColor whiteColor]];    header.textLabel.font = [UIFont systemFontOfSize:22.0 weight:UIFontWeightThin];}
```

In ios13, it is required that I create the background view myself:

```
- (void)tableView:(UITableView *)tableView willDisplayHeaderView:(UIView *)view forSection:(NSInteger)section{    UITableViewHeaderFooterView *header = (UITableViewHeaderFooterView *)view;    UIView *backgroundView = [UIView new];    header.backgroundView = backgroundView;    header.backgroundView.backgroundColor = [UIColor blueColor];    [header.textLabel setTextColor:[UIColor whiteColor]];    header.textLabel.font = [UIFont systemFontOfSize:22.0 weight:UIFontWeightThin];}
```