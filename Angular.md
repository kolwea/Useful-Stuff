  
  # Angular
  
  ## Firestore Setup
  
  constructor(private firestore: AngularFirestore) {}

  getSoundcloudData() {
    return this.firestore.collection('soundcloud').snapshotChanges();
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
