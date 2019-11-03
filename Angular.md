  
  # Angular
  
  ## Firestore Setup
  
  ```Typescript
  constructor(private firestore: AngularFirestore) {}

  getData() {
    return this.firestore.collection(<name>).snapshotChanges();
  }

  addEntryToDatabase(data) {
    return new Promise<any>((resolve, reject) => {
      this.firestore
        .collection(<name>)
        .add(data)
        .then(res => {
        }, err => reject(err));
    });
  }

  updateEntry(data) {
    return this.firestore
      .collection(<name>)
      .doc(data.payload.doc.id)
      .set({completed: true}, {merge: true});
  }

   ```
 
