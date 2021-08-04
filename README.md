# Pull request downloader

## About
Downloads all pull requests from repository.

## Execution
Replace URL (variable `start_urls`) in `get_pull_req.py` file and then:

```
conda create -n powp python=3
conda activate powp
python -m pip install -r requirements.txt
scrapy runspider get_pull_req.py
```

## Output
```
(powp) [ok@localhost powp]$ scrapy runspider get_pull_req.py 
https://github.com/iis-powp-2020/powp_jobs2d/pulls?page=1&q=is%3Aclosed
Pull request: /iis-powp-2020/powp_jobs2d/pull/53
Pull request: /iis-powp-2020/powp_jobs2d/pull/52
Pull request: /iis-powp-2020/powp_jobs2d/pull/51
...
Pull request: /iis-powp-2020/powp_jobs2d/pull/29
Pull request: /iis-powp-2020/powp_jobs2d/pull/28
Pull request: /iis-powp-2020/powp_jobs2d/pull/27
Pull request: /iis-powp-2020/powp_jobs2d/pull/26
Next page: /iis-powp-2020/powp_jobs2d/pulls?page=2&q=is%3Aclosed
Next page: /iis-powp-2020/powp_jobs2d/pulls?page=2&q=is%3Aclosed
https://github.com//iis-powp-2020/powp_jobs2d/pulls?page=2&q=is%3Aclosed
Pull request: /iis-powp-2020/powp_jobs2d/pull/25
Pull request: /iis-powp-2020/powp_jobs2d/pull/24
Pull request: /iis-powp-2020/powp_jobs2d/pull/23
...
Pull request: /iis-powp-2020/powp_jobs2d/pull/3
Pull request: /iis-powp-2020/powp_jobs2d/pull/2
Pull request: /iis-powp-2020/powp_jobs2d/pull/1
(powp) [ok@localhost powp]$ ls pull_requests/
11.html  16.html  20.html  25.html  2.html   34.html  39.html  43.html  6.html
12.html  17.html  21.html  26.html  30.html  35.html  3.html   45.html  7.html
13.html  18.html  22.html  27.html  31.html  36.html  40.html  4.html   8.html
14.html  19.html  23.html  28.html  32.html  37.html  41.html  53.html  9.html
15.html  1.html   24.html  29.html  33.html  38.html  42.html  5.html
```

## Fetch all pull requests as branches
Set the `.git/config` as below example (last line - _pull_)

```
[remote "origin"]
        url = https://github.com/iis-powp-2020/powp_jobs2d
        fetch = +refs/heads/*:refs/remotes/origin/*
        fetch = +refs/pull/*/head:refs/remotes/origin/pr/*
```
