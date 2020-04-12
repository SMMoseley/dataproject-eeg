
Edit this file to describe how to retrieve the data set. Except for very small data files, it's not recommended to check data into version control.
The data files are stored in .arf format which can be accessed using the h5py package. I have included a demo script that I ran that can retrieve the data off my computer. I had to download all the data from the lab servers onto my laptop because my VPN is not working and I do not have access to campus due to the COVID-19 pandemic. 
with h5.File('resources\P1\P1_20190912_mismatch_r1.arf','r') as P1:
    ls=list(P1.keys())
    print('List of datasets in this file:\n',ls)
    data=P1.get('rec_0')
    lsdata=list(data.keys())
    print('List of datasets in this file:\n',lsdata)
    rec0_Channel1get=data.get('channel0')
    Rec0_Channel1=np.array(rec0_Channel1get)
print (Rec0_Channel1)

I also can use this function to retrieve data and then follow up with selecting more specific data sections after I have assigned the file. 
def data_retrieval(filepath):
    Importeddata= h5.File(filepath,'r')
    return Importeddata   
