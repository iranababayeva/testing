all_links=[]
links2=[]
for g in range(1,100):
    page=requests.get(f'https://bina.az/items/all?page={g}')
    html=BeautifulSoup(page.content,'html.parser')
    html1=html.findAll('a')
    for link in html1:
        all_links.append(link.get('href'))
    for i in range(len(all_links)):
        a=str(all_links[i])
        if a.find('items')>0 and len(a)==14 and ('https://bina.az/'+a) not in links2:
            links2.append('https://bina.az/'+a)   
            
