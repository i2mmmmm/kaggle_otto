# kaggle_otto



train_1 = pd.DataFrame()
chunks = pd.read_json('train.jsonl', lines=True, chunksize=500000)

for e, chunk in enumerate(chunks):
    event_dict = {
        'session': [],
        'aid': [],
        'ts': [],
        'type': [],
    }
    if e < 2:
        # train_1 = pd.concat([train_sessions, chunk])
        for session, events in zip(chunk['session'].tolist(), chunk['events'].tolist()):
            for event in events:
                event_dict['session'].append(session)
                event_dict['aid'].append(event['aid'])
                event_dict['ts'].append(event['ts'])
                event_dict['type'].append(event['type'])
        chunk_session = pd.DataFrame(event_dict)
        train_1 = pd.concat([train_1, chunk_session])
    else:
        break
        
train_1 = train_1.reset_index(drop=True)
